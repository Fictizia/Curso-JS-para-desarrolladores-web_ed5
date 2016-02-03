# Clase 3

### OpenExpo

![OpenExpo_logo](http://www.openexpo.es/wp-content/uploads/2015/12/openexpo-logo-claim6.png)

**OpenExpo 2016 – The Future is Open**

OpenExpo 2016, III Feria y Congreso anual sobre FLOSS y Open World Economy (Open Data y Open Innovation) que reúne en Madrid a más de 2.000 personalidades del sector, profesionales y empresas en búsqueda de generación de negocio.

El objetivo de OpenExpo es difundir, presentar, descubrir y evaluar las soluciones y las tendencias de la industria que ofrece el Open Source & Software Libre y Open World Economy (Open Data y Open Innovation).

- Encuentro con más de 2.000 profesionales senior del sector en solo un día: representantes de las principales empresas e instituciones, desarrolladores de código abierto, hackers, expertos, proveedores y usuarios de todos los niveles.
- Mayor retorno de la inversión a través de oportunidades de exhibición, conferencias y de patrocinio.
- Amplíe el alcance de su marca a través de nuestra plataforma de marketing multi-canal.
- Un día de conferencias, casos de éxito, Keynotes, talleres, mesas redondas, demos y otras actividades paralelas en torno al mundo de las tecnologías libres.
- Más de 100 empresas participantes que presentarán sus novedades y soluciones tecnológicas.

- [Más info](http://www.openexpo.es/)
- [Entradas gratuitas hasta finales de Febrero](http://www.openexpo.es/openexpo-2016/inscripcion)


### Ejercicios de Pseudocódigo:

11 - Diseña un algoritmo que nos confirme si un [año es bisiesto](https://es.wikipedia.org/wiki/A%C3%B1o_bisiesto) o no.
- Caracteristicas de un año bisiesto:
	- Tiene que ser divisible entre 4 y no tiene que ser divisible entre 100
	- O puede ser divisble entre 100 y entre 400
```
    // Tu solución
```

12 - Diseña un algoritmo que imprima los numeros del 1 al 100.
```
    // Tu solución
```

13 - Diseña un algoritmo que imprima los numeros del 100 al 0.
```
    // Tu solución
```

14 - Diseña un algoritmo que imprima los numeros pares entre 0 y 100.
```
    // Tu solución 
```

15 - Diseña un algoritmo que imprima los números impares entre un número dado por el usuario y los siguientes 50 números.
```
    // Tu solución
```

16 - Diseña un algoritmo que imprima la suma de los 50 primeros numeros pares y el total de números impares partiendo de un número dado por el usuario
```
    // Tu solución
```


17 - Diseña un algoritmo que cuente las veces que aparece una determinada letra en una frase que introduciremos por teclado.
```
    // Tu solución
```

19 - Diseña un algoritmo que simula el lanzamiento de una moneda al aire e imprimir si ha salido cara o cruz.
```
    // Tu solución
```

20 - Diseña un algoritmo que  simula cien tiradas de dos dados y contar las veces que entre los dos suman 10.
```
    // Tu solución
```


### JSHint
- [JSHint Online](http://jshint.com/)
- [JSHint About](http://jshint.com/about/)
- [JSHint Repository](https://github.com/jshint/jshint)

### Consola

- [@ChromeDevTools en Twitter](https://twitter.com/chromedevtools?lang=es)
- [Chrome DevTools](https://developer.chrome.com/devtools)

**Métodos:**
- .assert() *Aparece un mensaje de error en la consola si la afirmación es falsa.*:
```javascript
 var controlador = false;
 console.assert(controlador, "\"controlador\" es igual a \"false\"");
```

- .clear() *Limpia la consola*:
```javascript
 console.clear()
```


- .dir() *Retorna una lista interactiva de las propiedades de un objeto*:
```javascript
 console.dir(document.body);
```

- .dirxml() *Retorna una representación HTML del objeto*:
```javascript
 console.dirxml(document.body);
```


- Agrupadores:
 - .group() *Crea un grupo de mensajes de consola*:
 ```javascript
     console.group("bucleFor");
     for(var i=100; i>0; i--){
         console.info("Iteración numero %i", i)
     }
     console.groupEnd();
 ```
 - .groupCollapsed() *Crea un grupo de mensajes de consola minimizados (por defecto)*:
 ```javascript
     console.groupCollapsed("bucleFor");
     for(var i=100; i>0; i--){
         console.info("Iteración numero %i", i)
     }
     console.groupEnd();
 ```
 - .groupEnd() *Cierra el grupo de mensajes*:
 ```javascript
     console.group("bucleFor");
     for(var i=100; i>0; i--){
         console.info("Iteración numero %i", i)
     }
     console.groupEnd();
 ```


- Tablas:
 - .table() *Muestra los datos dentro de una tabla*:
 ```javascript
 var lenguajes = [
     { nombre: "JavaScript", extension: ".js" },
     { nombre: "TypeScript", extension: ".ts" },
     { nombre: "CoffeeScript", extension: ".coffee" }
 ];
 
 console.table(lenguajes);
 
 console.table(lenguajes, "extension");
 ```

- Gestión del tiempo:
 - .time() *Inicia un contador en ms*:
 - .timeEnd() *Para el contador y devuelve el resutlado*:
 ```javascript
  console.time("Medición de miArray");
  var miArray = new Array(1000000);
  for (var i = miArray.length - 1; i >= 0; i--) {    
   miArray[i] = new Object();
  };
  console.timeEnd("Medición de miArray");
 ```

- Notificadores:
 - .log() *Saca un mensaje por consola*:
 ```javascript
  console.log("Hola en formato clásico");
 ```
 - .info() *Similar a console.log*:
 ```javascript
  console.info("Hola en formato informativo");
 ```
 - .warn() *Similar a Console.log*:
 ```javascript
  console.warn("Hola en formato alerta");
 ```
 - .error() *Similar a console.log, invcluye *:
 ```javascript
  console.error("Hola en formato error");
 ```

- Formateadores:

Formato | Descripción
------------ | -------------
%s | Cadena
%d o %i | Número entero
%f | Decimal
%o | DOM
%O | Objeto js
%c | CSS

- Ejemplos:
 - *%o* para estrcuturas del DOM
 ```javascript
  var parrafos = document.getElementsByTagName("p");
  console.log("DOM: %o", parrafos);
 ```
 - *%O* para objectos JS
 ```javascript    
  var objeto = {"nombre":"Yo","Apellido":"Mismo"};
  console.log("Objeto: %O", objeto);
 ```
 - usando CSS:
 ```javascript
  console.log('Esto es aburrido...');
  console.log('%c Pero se puede mejorar fácilmente! ', 'background: #3EBDFF; color: #FFF; font-size:25px;');
 ```


### Ejercicios

**Recuerda:** Utiliza [JSHint](http://jshint.com/) para detectar errores..

**1 -** Utiliza .assert para controlar cuando se muestra tu nombre por consola.
```javascript
    // Tu solución
```

**2 -** Crea un script que nos permita calcular el tiempo que se necesita para realizar la siguientes acciones.
- Especificaciones:
	- Imprimir tu nombre usando **console.log, console.info, console.warn**
```javascript
    // Tu solución
```

**3 -** Partiendo del ejercicio anterior mejora los estilos de cada mensaje usando estilos.
```javascript
    // Tu solución
```

**4 -** Agrupa cada tipo de mensaje y añade un contador de tiempo por cada grupo.
```javascript
    // Tu solución
```

**5 -** Crea una tabla usando la consola para mostrar el nombre de tus compañeros y el puesto que ocupa en la clase.
```javascript
    // Tu solución
```



### Comentarios
- Una línea
```javascript
// Comentario en una línea
```
- Multiples Líneas
```javascript
/*
Una Línea....
Otra linea...
Etc...
*/
```

### Variables

- No se pueden usar espacios
```javascript
var con espacios = 1;
```

- No usar un número delante
```javascript
var 1numero = 1;
```

- Válidos, pero no recomendado
```javascript
var con_guiones_bajos = 1;
var dame$ = 1;
```

- Válidos, es mejor usar [camelCase](https://es.wikipedia.org/wiki/CamelCase)
```javascript
var otraOpcion = 1;
var opcionCon123123 = 1;
```


### Tipos de variables

Operador *typeof* y su [especificación](http://www.ecma-international.org/ecma-262/5.1/#sec-11.4.3)

- [x] Undefined
```javascript
typeof undefined
typeof noDefinido
typeof tampocoCreado
```

- [x] Object
```javascript
typeof null
typeof [15, 4]
typeof new Date()
typeof {a:1}
```

- [x] Boolean
```javascript
typeof false
typeof true
typeof Boolean(false)
```

- [x] Number
```javascript
typeof 3
typeof 3.14
typeof NaN
typeof Infinity
```

- [x] String
```javascript
typeof "hola"
```

- [x] Function
```javascript
typeof function(){}
typeof class C {}
```


### Matemáticas Básicas
```javascript
var suma = 5 + 4;
var resta = 10 - 6;
var multiplicacion = 3 * 3;
var division = 6 / 2;
var modulo = 43 % 10;

function calcular (operacion) {
    console.log(operacion);
};
```

### Matemáticas Básicas (Agrupando operaciones)
```javascript
var expresion1 = (3 + 7) * 10;
var expresion2 = (-56 * 6) - 74 * -25;
var expresion3 = (3 * 3) + 10 - 12 / 2;
var expresion4 = 44 + (83 % (33 + 100));
var expresion5 = -145 + (500 / 10 - 5) + 10 * 10 ;

function calcular (operacion) {
    console.log(operacion);
};
```

### Matemáticas Básicas (crecimiento y decrecimiento)
```javascript
var numero = 5;

console.log(--numero); // 4
console.log(numero--); // 5 (luego 4)
console.log(++numero); // 6
console.log(numero++); // 5 (luego 6)
```

### Operadores de asignación
- = *Asignacion*
```javascript
var x = 1;
var y = 2;
x = y;
console.info("\"x\" vale ", x);
```

- += *Suma*
```javascript
var x = 1;
var y = 2;
x += y;
console.info("\"x\" vale ", x); // x = x + y
```

- -= *Resta*
```javascript
var x = 1;
var y = 2;
x -= y;
console.info("\"x\" vale ", x); // x = x - y
```

- *= *Multiplicación*
```javascript
var x = 1;
var y = 2;
x *= y;
console.info("\"x\" vale ", x); // x = x * y
```

- /= *División*
```javascript
var x = 1;
var y = 2;
x /= y;
console.info("\"x\" vale ", x); // x = x / y
```

- %= *Resto*
```javascript
var x = 1;
var y = 2;
x %= y;
console.info("\"x\" vale ", x); // x = x % y
```


**Jugando con variables**

```javascript
var empezoComo3 = 3;
era3();

empezoComo3 = 35;
era3();

empezoComo3 = empezoComo3 + 30;
era3();

empezoComo3 += 4;
era3();

empezoComo3++;
era3();

empezoComo3 -= 12;
era3();

empezoComo3--;
era3();

empezoComo3 *= 10;
era3();

empezoComo3 /= 11;
era3();

empezoComo3 += "texto";
era3();

empezoComo3 += 20;
era3();

empezoComo3++;
era3();


function era3 () {
    console.log("empezoComo3 debería ser 3, ahora su valor es " + empezoComo3);
};
```


### Interacción Básica con el Usuario

- alert():
    ```javascript
    alert("¡Bienvenido a esta web!");
    ```

- confirm():
    ```javascript
    confirm("¿Esta seguro que desea abandonar esta web?");
    ```


- Ejemplo:
    ```javascript
    var respuesta = confirm("presiona un botón!");
    if (respuesta === true) {
        console.log("Has aceptado!");
    } else {
        console.log("Has cancelado");
    }
    ```

- prompt():
    ```javascript
    prompt("¿Como te llamas?");
    ```

- Registremos los datos en una variable:
    ```javascript
    var nombre = prompt("¿Como te llamas?");
    ```

### Ejercicios

**1 -** Vamos a solicitar la colaboración del usuario para lograr nuestros objetivos:
- Objetivos:
	-  Captura el nombre del usuario usando prompt
	-  Pregunta al usuario si desea *"comprobar lo rápido que funcioan su navgador"*.
	-  En caso afirmativo imprimiremos el nombre del usuario por consola aplicandole estilos y calculando el tiempo que tarda en realizar la operación
- En caso negativo mostraremos un *alert* informativo.
```javascript
    // Tu solución
```

### Modo Estricto
> El modo estricto hace varios cambios en la semántica normal de JavaScript. Primero, modo estricto elimina algunos errores silenciosos de JavaScript cambiando a que lance los errores. Segundo, modo estricto corrige errores que hacen que sea difícil para los motores de JavaScript para realizar optimizaciones: código de modo estricto a veces se puede hacer para correr más rápido que el código idéntico que no es estricto. Tercero, el modo estricto prohíbe sintaxis que es probable que sea definida en futuras versiones de ECMAScript.
> - [Mozilla](https://developer.mozilla.org/es/docs/Web/JavaScript/Referencia/Modo_estricto)

- [Compatibilidad](http://caniuse.com/#feat=use-strict)

En resumen:
- Detectaremos más errores
- Mejora la interpretación, lo que aumenta la velocidad de ejecucción.
- Previene que usemos sintaxis de futuras versiones de ECMAScript.

Aplicándolo a todo nuestro código

```javascript
// ./script.js
(function() {
  "use strict";

  // Nuestro código

})();
```

Aplicándolo solo en parte del código
```javascript
// ./script.js
function estricta(){
  'use strict';
  function anidada() {
      return "Yo también!";
  }
  return "Hola! Soy una función en modo estricto!  " + anidada();
}

function noEstricta() {
    return "yo no soy una función estricta.";
}
```

Algunos ejemplos:

- Error: Usar variables u objetos sin declararlos antes.

```javascript
    function estricto(){
        'use strict';
        pi = 3.14;
        console.log(pi);
    }
```

- Error: Borrar variables, objetos o funciones. 

```javascript
    function estricto(){
        'use strict';
        pi = 3.14;
        delete pi
    }
```

- Error: Duplicar parámetros

```javascript
    function estricto(){
        'use strict';
        function x (p1, p1){
            // código
        }
    }
```

- Error: Al usar carácteres escapados
 
```javascript
    function estricto(){
        'use strict';
        var x = \010; 
    }
```

Error: Al usar *writable:false*

```javascript
    function estricto(){
        'use strict';
        var obj = {};
        Object.defineProperty(obj, "x", {value:0, writable:false});
        obj.x = 3.14;
    }
```

Error: Al usar *with* 

```javascript
    function estricto(){
        'use strict';
        with (Math){x = cos(2)};
    }
```

Error: Al usar *eval()* por seguridad

```javascript
    function estricto(){
        'use strict';
        eval ("var x = 2");
        console.log(x);
    }
```



Otras palabras reservadas en modo estricto:
- implements
- interface
- let
- package
- private
- protected
- public
- static
- yield


**Ejercicios:**

1 - Diseña un algoritmo que lea dos números y realice los siguientes cálculos:
- Valor de su suma
- Valor de su resta
- Valor de su division
- Valor de su producto

```javascript
    // Tu solución
```

2 - Diseña un algoritmo para calcular el porcentaje de hombres y mujeres en nuestro curso.
- Trucos:
	- Calcular porcentajes (segmento*100)/total

```javascript
	// Tu solución
```
