# Clase 15

### JSDocs

```javascript

/** @namespace */
var app = {};

/**
 * Resuelve la división de a/b
 * @example
 * // retorna 3
 * globalNS.metodo(5, 15);
 * @returns {Number} Retorna el resultado de la operación.
 */
app.metodo = function (a, b) {
    return b / a;
};
```

- [Documentación oficial](http://usejsdoc.org/tags-example.html)
- [Speaking JavaScript (Axel Rauschmayer) - Chapter 29. JSDoc: Generating API Documentation](http://speakingjs.com/es5/ch29.html)

### Guías de estilo

- [idiomatic.js](https://github.com/rwaldron/idiomatic.js/)
- [MDN Coding style](https://developer.mozilla.org/en-US/docs/Mozilla/Developer_guide/Coding_Style#JavaScript_practices)
- [Airbnb JavaScript Style Guide](https://github.com/airbnb/javascript)
- [Google JavaScript Style Guide](https://google.github.io/styleguide/javascriptguide.xml)


> Todo el código en cualquier proyecto debería verse como si una sola persona lo hubiera escrito, sin importar cuánta gente haya contribuído. 
> Idiomatic.js

Desventajas:
- Adopción total del equipo
- Curva de aprendizaje
- Falta de plugins

### Versionamiento Semántico (Semver)

![img](https://blog.gopheracademy.com/postimages/advent-2015/semver.png)
[semver](http://semver.org/lang/es/)

### Expresiones Regulares 

- **Recursos:**
    - [10 Expresiones Regulares Imprescindibles en Desarrollo Web](http://web.ontuts.com/snippets/10-expresiones-regulares-imprescindibles-en-desarrollo-web/)
    - [Common Regular Expressions in Javascript](http://geniuscarrier.com/common-regular-expressions-in-javascript/)

- **Documentación:**
    - [Expresiones Regulares en MDN](https://developer.mozilla.org/es/docs/Web/JavaScript/Guide/Regular_Expressions)

- **Herramientas:**
    - [regexr](http://regexr.com/) 
    - [Regular Expressions Cheat Sheet by DaveChild](http://www.cheatography.com/davechild/cheat-sheets/regular-expressions/)

### Require.js & AMD

![Require & AMD logo](http://d348unuw4205d6.cloudfront.net/wp-content/uploads/2014/06/amd_and_require.jpg)

- *Asincronia*
![Asincronia](http://www.codeproject.com/KB/scripting/625262/AMD.png)

- *Dependencias y modularidad*
![Modularidad](http://1.bp.blogspot.com/-RWKQH6r6AQ8/Uutpgj0letI/AAAAAAAAAnk/Rd7hmZ-0-Rg/s1600/fig01.png)


**Entendiendo la utilidad de Require.js**
- Código convencional (Código espagueti):
  - [Código espagueti](https://www.wikiwand.com/es/C%C3%B3digo_espagueti)
  - index.html:
  ```html
    <!doctype html>
    
    <html lang="en">
    <head>
      <meta charset="utf-8">
    
      <title>Testing Requirejs</title>
    
    
    </head>
    
    <body>
      <script src="calculadora.js"></script>
    </body>
    </html>
  ```

  - calculadora.js
  ```javascript
  function sumar (x, y) {
      return x+y
  };
  
  function restar (x, y) {
      return x-y
  };
  
  function multiplicar (x, y) {
      return x*y
  };
  
  
  function dividir (x, y) {
      return x/y
  };
  ```

- Código convencional (Creando un objeto):

  - calculadora.js
  ```javascript
  var calculadora = {};

  calculadora.sumar = function (x,y) {
      return x + y
  };
  calculadora.restar = function (x, y) {
      return x - y
  }
  calculadora.multiplicar = function (x, y) {
      return x * y
  }
  calculadora.divir = function (x, y) {
      return x / y
  }
  ```
  
  
- Código convencional (Mejorando la escalabilidad "dividiendo el objeto"):
  - index.html:
  ```html
  <script src="sumar.js"></script>
  <script src="restar.js"></script>
  <script src="divir.js"></script>
  <script src="multiplicar.js"></script>
  ```
  
  - /sumar.js
  ```javascript
  var calculadora = calculadora || {};
  calculadora.sumar = function (x,y) {
      return x + y
  };
  ```
  
  - /restar.js
  ```javascript
  var calculadora = calculadora || {};
  calculadora.restar = function (x, y) {
      return x - y
  }
  ``` 

  - /dividir.js
  ```javascript
  var calculadora = calculadora || {};
  calculadora.divir = function (x, y) {
      return x / y
  }
  ```


  - /multiplicar.js
  ```javascript
  var calculadora = calculadora || {};
  calculadora.multiplicar = function (x, y) {
      return x * y
  }
  ```


**Usando Require.js**
- AMD:
  - [Asynchronous module definition](https://www.wikiwand.com/es/Asynchronous_module_definition)
  
  - index.html:
  ```html
  <script data-main="calculadora" src="require.js"></script>
  ```
  - /calculadora.js
  ```javascript
  require(['calculadora/sumar', 'calculadora/restar', 'calculadora/cuadrado'], function (sum, res, cua) {
    console.info(sum(1,2)); // 1 + 2
    console.info(res(3,1)); // 3 - 1 
    console.log(cua(2)); // 2 * 2
  });
  ```

  - calculadora/sumar.js
  ```javascript
  define(function () {
    return function (x, y) {
        return x + y;
    };
  });
  ```

  - calculadora/restar.js
  ```javascript
  define(function () {
    return function (x, y) {
        return x - y;
    };
  });
  ```

  - calculadora/multiplicar.js
  ```javascript
  define(function () {
    return function (x, y) {
        return x * y;
    };
  });
  ```

  - calculadora/cuadrado.js
  ```javascript
  define(['calculadora/multiplicar'], function (multiplicar) {
    return function (x) {
        return multiplicar(x, x);
    };
  });
  ```


**Require.js - Modo Avanzado**

- Require.js con dependencias externas:
  - vendor/jquery.min.js (en local)

  - script.js
  ```javascript
  require(['vendor/jquery'], function($){
      $('#hola').html("<h1>HOLA! Hola!</h1>");
  });
  ```


- Require.js varios modulos en el mismo archivo:
  - script.js
  ```javascript
  require(['hola', 'adios'], function(hola, adios){
      $('#hola').html("<h1>"+hola+" y "+adios+"!</h1>");
  });
  ```

  - hola.js
  ```javascript
  define(function() {
      return "Hola";
  });
  
  define('adios', function() {
      return "adios";
  });
  ```

- Require.js configurando baseUrl:

  - Estructura del proyecto: 
  ```  
    www/
        /assets/
        /css/
        /js/
            /App/
                main.js
        /vendor/
            bootstrap.js
            jquery.js
  ```

  - config.js:
  ```javascript    
  requirejs.config({
      baseUrl: '.assets/js'
  });
  ```
  
  - *.js
  ```javascript 
  require(['vendor/jquery', 'vendor/bootstrap', 'app/main']);
  ```


- Require.js configurando Paths:

  - Estructura del proyecto: 
  ```  
    www/
        /assets/
        /css/
        /js/
            /app/
                main.js
        /vendor/
            bootstrap.js
            jquery.js
                
  ```  

  - config.js:
  ```javascript 
  requirejs.config({
      baseUrl: '.assets/js',
      paths: {
          'jquery': 'vendor/jquery',
          'bootstrap': 'vendor/bootstrap',
          'main': 'app/main'
      }
  });
  ```
  
  - *.js:
  ```javascript 
  require(['jquery', 'bootstrap', 'main']);
  ```

### Rendimiento
- [jsPerf](http://jsperf.com/)
- [benchmark.js](http://benchmarkjs.com/)


### Mundo Node

![Node_logo](https://nodejs.org/static/images/logos/nodejs.png)
- Comprobar version:
```
    node -v
```

**NPM**

![npm_logo](http://ohdoylerules.com/content/images/npm-logo.svg)

- Comprobar version:
```
    npm -v
```

**package.json**

- Datos proyecto
- Tareas
- Dependencias (dependencies y devDependencies)

- Dependency Hell:
  - [Nodei.co](https://nodei.co/)
  - [Dependency Hell](http://www.wikiwand.com/en/Dependency_hell)
  - [David Dm](https://david-dm.org/)
    - [Ejemplo Twitter-sentiments](https://david-dm.org/UlisesGascon/twitter-sentiments#info=dependencies&view=list)
    - [Ejemplo Grunt](https://david-dm.org/gruntjs/grunt#info=dependencies&view=table)
    - [Ejemplo Express](https://david-dm.org/strongloop/express)
    - [Ejemplo Bower](https://david-dm.org/bower/bower#info=dependencies&view=table)
  - [ShieldsIO](http://shields.io/)
    - [Your Badge Service](http://badges.github.io/gh-badges/) 

Seguridad:
  - [Seguridad](https://nodesecurity.io/resources)
  - [Seguridad Avisos](https://nodesecurity.io/advisories)


- Hello World con HTTP:
```javascript
  var http = require('http');
  
  var puerto = 3000;
  var direccion = "127.0.0.1";
  var mensaje = 'Hola a todos, ahora usando HTTP\n';
  
  
  http.createServer(function (req, res) {
    res.writeHead(200, {'Content-Type': 'text/plain'});
    res.end(mensaje);
  }).listen(puerto, direccion);
  console.log('Server running at http://'+direccion+':'+puerto+'/');
```

- Hello World desde c9.io:
```javascript
  var http = require('http');
  
  var mensaje = 'Hola a todos, ahora usando HTTP con C9.io\n';
  
  http.createServer(function(req, res) {
      res.writeHead(200, {'Content-Type': 'text/plain'});
      res.end(mensaje);
  }).listen(process.env.PORT, process.env.IP);
  
  console.log('Server running at http://'+process.env.IP+':'+process.env.PORT+'/');
```

- Rediccionamiento:
```javascript
  var http = require('http');
  
  http.createServer(function (req, res) {
    res.writeHead(301, {
      'Location': 'http://www.google.es/'
    });
      res.end();
  }).listen(process.env.PORT, process.env.IP);
  
  console.log('Servidor funcionando en http://'+process.env.IP+':'+process.env.PORT+'/');
```


**Bower**

![Bower Logo](http://image.slidesharecdn.com/bower-phxjs-140515152011-phpapp02/95/bower-phoenix-javascript-meetup-1-638.jpg?cb=1400167728)

> Web sites are made of lots of things — frameworks, libraries, assets, utilities, and rainbows. Bower manages all these things for you.

- [Bower](http://bower.io/)
- [Tendencias Bower](http://bower.io/stats/)
- [Buscador Bower](http://bower.io/search/)


**Gulp**

![Gulp](http://anexsoft.com/uploads/60dbd15f5f2a87bc51375dbcaa7e4f05.jpg)
![Gulp_anatomy](http://i2.wp.com/joellongie.com/wp-content/uploads/2015/02/web-gulp-anatomy.jpg)
- [Grunt vs. Gulp](http://www.slideshare.net/appleboy/automating-your-workflow-with-gulp)
- [Quenchjs - Generador web](http://quenchjs.com/)

- Plugins destacados:
    - [Todos los Plugins](http://gulpjs.com/plugins/)
    - [uncss](https://www.npmjs.com/package/gulp-uncss/)
    - [gulp-load-plugins](https://www.npmjs.com/package/gulp-load-plugins/)
    - [gulp-clean](https://github.com/peter-vilja/gulp-clean)
    - [gulp-concat](https://github.com/contra/gulp-concat)
    - [gulp-uglify](https://github.com/terinjokes/gulp-uglify)
    - [gulp-reveal](https://www.npmjs.com/package/gulp-reveal)

**Yeoman**
![Yeoman Logo](https://raw.githubusercontent.com/yeoman/media/master/optimized/yeoman-masthead.png)
> The Yeoman workflow comprises three types of tools for improving your productivity and satisfaction when building a web app: the scaffolding tool (yo), the build tool (Grunt, Gulp, etc) and the package manager (like Bower and npm).

- [Yeoman Instalation Working Flow](https://www.youtube.com/watch?v=zBt2g9ekiug)
- [Yeoman - Generator-webapp](https://github.com/yeoman/generator-webapp)
- [Yeoman - Santa Barbara JavaScript Meetup](http://www.slideshare.net/tim_doherty/yeoman-santa-barbara-bjava-scriptmeetup)
- [Automating Your Front-end Workflow with Yeoman 1.0 (Addy Osmani)](https://www.youtube.com/watch?v=1OAfGm_cI6Y)



**Express**

![Express_logo](https://i.cloudup.com/zfY6lL7eFa-3000x3000.png)

- Middelware
![Mw_schema](http://image.slidesharecdn.com/introtonode-140914093424-phpapp01/95/intro-to-nodejs-14-638.jpg?cb=1410687757)



**Jade**

![Jade_logo](https://avatars0.githubusercontent.com/u/9338635?v=3&s=400)


### Extras

**[El largo camino del desarrollador web](https://coggle.it/diagram/52e97f8c5a143de239005d1b/56212c4e4c505e0045c0d3bda59b77e5977c2c9bd40f3fd0b451bdcf8da4aa52)**

- Front-End
- back-End
- Fullstack
- Dev Ops
- etc...

**[¿Cómo seguir aprendiendo después de este curso?](extra.md)**