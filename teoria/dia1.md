# Clase 1

### JavaScript

![js_logo](http://www.fictizia.com/assets/styles/styleImgs/wideBox/widebox_js.png)

> JavaScript (abreviado comúnmente JS) es un lenguaje de programación interpretado, dialecto del estándar ECMAScript. Se define como orientado a objetos, basado en prototipos, imperativo, débilmente tipado y dinámico.

> Se utiliza principalmente en su forma del lado del cliente (client-side), implementado como parte de un navegador web permitiendo mejoras en la interfaz de usuario y páginas web dinámicas aunque existe una forma de JavaScript del lado del servidor (Server-side JavaScript o SSJS). Su uso en aplicaciones externas a la web, por ejemplo en documentos PDF, aplicaciones de escritorio (mayoritariamente widgets) es también significativo. [JavaScript Wikiwand](https://www.wikiwand.com/es/JavaScript)


**Características**
- Multiparadigma
- Imperativo y estructurado
- Dinámico
	- Tipado dinámico
	- Objetual
	- Evaluación en tiempo de ejecución
- Funcional
	- Funciones de primera clase
- Prototípico	
	- Prototipos
	- Funciones constructoras
- Entorno de ejecución
- Funciones varídicas	
- Funciones como métodos
- Arrays y la definición literal de objetos
- Expresiones regulares

**[ECMA-262](https://www.wikiwand.com/es/ECMAScript)**
- Versiones:
	- Versión 1 (Junio de 1997)
	- Versión 2 (Junio de 1998)
	- Versión 3 (Diciembre de 1999)
	- Versión 3 (Abandonado)
	- Versión 5 (Diciembre de 2009)
	- Versión 5.1 (Diciembre de 2011)
	- Versión 6 (Junio de 2015)
	- Versión 7 (En desarrollo)

- **Compatibilidad:**
	- [ECMA6](https://kangax.github.io/compat-table/es6/)
	- [ECMA5](http://kangax.github.io/compat-table/es5/)
	- [Non-standard](http://kangax.github.io/compat-table/non-standard/)
	- [HTML5 & CSS3](http://fmbip.com/litmus/)
	- [Polyfill](https://www.wikiwand.com/en/Polyfill)

- **Compiladores**
	- [Coffeescript](http://coffeescript.org/)
	- [Typescript](http://www.typescriptlang.org/)
	- [Livescript](http://livescript.net/)

- **Librerías**
	- [underscore](http://underscorejs.org/)
	- [Jquery](https://jquery.com/)
	- [Microjs](http://microjs.com/#)
	- [Threejs](http://threejs.org/)
	- [D3.js](http://d3js.org/)
	- [Modernizr](https://modernizr.com/)
	- [Lodash](https://lodash.com/)
	- [mustache.js](https://github.com/janl/mustache.js)
	- [handlebars.js](http://handlebarsjs.com/)
	- [Firebase](http://firebase.com/)
- **Frameworks (MV*)**
	- [Angular.js](https://angularjs.org/)
	- [Ember.js](http://emberjs.com/)
	- [Backbone.js](http://backbonejs.org/)
	- [KnockOut.js](http://knockoutjs.com/)
	- [React](http://facebook.github.io/react/)
	- [Meteor](https://www.meteor.com/)

- **JavaScript en el servidor**
	- [Node.js](https://nodejs.org/en/)
	- [Grunt](http://gruntjs.com/)
	- [Gulp](http://gulpjs.com/)
	- [Express](http://expressjs.com/es/)
	- [MongoDB](https://www.mongodb.org/)
	- [Socket.io](http://socket.io/)

- **[El estado del desarrollo Front-End en 2015 por Ashley Nolan](http://ashleynolan.co.uk/blog/frontend-tooling-survey-2015-results)**


### Entorno de desarollo moderno
![Diversos Entornos](http://www.rittmanmead.com/wp-content/uploads/2013/01/NewImage1.png)

### Control de Versiones

**Bienvenidos a la maquina del tiempo**
- Arquitectura de Árbol(working area, staging Area, Repository)
- Auditoria de código (quien? cuando? y que?)
- Git trabaja en binario (imagenes, docs, etc...)
- Git no guarda una copia de cada version, solo los cambios.
- Distribución (Repositorios y Clones)
- Opensource y funciona offline
- Consola vs. GUI

**Trabajo efectivo**

- [Clientes escritorio](https://mac.github.com)
- [Consola (Cheat-sheet)](https://training.github.com/kit/downloads/es/github-git-cheat-sheet.pdf)
- Repositorio
- Tracking
- Commits
- Sincronizar cambios
- Ramas
- Fork
- Clonación
- Pull-request
- Gestión de merges
- Público/Privado

**Working Flow**

![Como trabajar con Git](http://nvie.com/img/git-model@2x.png)


### Github

- [Socializacion](https://guides.github.com/activities/socialize/)
	- Perfil
- Timeline Actividad
- [Colaborar](https://guides.github.com/activities/contributing-to-open-source/)
- [Compartir](https://guides.github.com/introduction/getting-your-project-on-github/)
- [Gist](https://gist.github.com/)
- [Issues](https://guides.github.com/features/issues)
- [Pages](https://guides.github.com/features/pages/)
- [Wikis](https://guides.github.com/features/wikis)


### C9.io

*Creamos una cuenta y un workespace con referencia a nuestro repositorio de GitHub*
- [c9.io](https://c9.io/)

### C9.io (Control de versiones)

**GIT (comandos)**

![Trabajar con Git/Github](http://www.geekgumbo.com/wp-content/uploads/2011/08/nvie-git-workflow-commands.png)


**Quiero subir algo a Github**

1. Verificamos el estado en general.
 ```
git status
 ```

2. Nos actualizamos.
 ```
git pull
 ```

3. Preparamos nuestro commit (añadimos archivos y añadimos la información adicional)
 ```
git add "ARCHIVO"
git commit -m "MENSAJE..."
 ```

4. Actualizamos y enviamos los cambios a Github
 ```
git pull && git push
 ```


**No quiero subir nada a Github, pero quiero estar actualizado**

1. Verificamos el estado en general.
 ```
git status
 ```

2. Nos actualizamos.
 ```
git pull
 ```


**Trucos:**

Si usais este [comando](https://git-scm.com/docs/git-credential-cache/1.7.12.1):

```
git config --global credential.helper 'cache --timeout=9999999'
```
Git cacheará la sesión y no os preguntará el usuario o la password durante 9999999ms (2,7h).


**Ejercicios**

**1 -** Sube tu código a GitHub

- Crea una carpeta en el repositorio con tu nombre.
- Una subcarpeta *pública* y otra *privada*
- Crea un archivo *Hello Word* usando [Markdown](https://guides.github.com/features/mastering-markdown/)
- Comparte la tu carpeta *pública* con todos nosotros en GitHub

**2 -** Crea un [Gist](https://gist.github.com/) con el esqueleto de un index.html

**3 -** Presentate en este [issue](https://github.com/UlisesGascon/curso-js-web-developers-012016/issues/1)
