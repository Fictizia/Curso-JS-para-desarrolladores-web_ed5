# Clase 4 Ejercicios
## Consola
### Ejercicios


**1 -** Utiliza .assert para controlar cuando se muestra tu nombre por consola.

```javascript
var controlador = false;
console.assert(controlador, "Hola !!!, soy Juan Belmonte");
```

**2 -** Crea un script que nos permita calcular el tiempo que se necesita para realizar la siguientes acciones.
- Especificaciones:
- Imprimir tu nombre usando **console.log, console.info, console.warn**

```javascript
var nombre = "Juan Belmonte";

console.time("presentación");
console.log("Hola !!!, soy " + nombre);
console.info("Hola !!!, soy " + nombre);
console.warn("Hola !!!, soy " + nombre);
console.timeEnd("presentación");
```

**3 -** Partiendo del ejercicio anterior mejora los estilos de cada mensaje usando estilos.

```javascript
var nombre = "Juan Belmonte";

console.time("presentación");
console.log("%c Hola !!!, soy " + nombre, "background-color: green; color: brown; font-size: 20px;");
console.info("%c Hola !!!, soy " + nombre, "background-color: pink; color: cyan; font-size: 40px;");
console.warn("%c Hola !!!, soy " + nombre, "background-color: crimson; color: black; font-size: 60px;");
console.timeEnd("presentación");
```

**4 -** Agrupa cada tipo de mensaje y añade un contador de tiempo por cada grupo.

```javascript
var nombre = "Juan Belmonte";


// Grupo del Mensaje console.log
console.group("Grupo console log");
	console.time("presentación console.log");
		console.log("%c Hola !!!, soy " + nombre, "background-color: green; color: brown; font-size: 20px;");
	console.timeEnd("presentación console.log");
console.groupEnd();

// Grupo del Mensaje console.info
console.group("Grupo console info");
	console.time("presentación console.info");
		console.info("%c Hola !!!, soy " + nombre, "background-color: pink; color: cyan; font-size: 40px;");
	console.timeEnd("presentación console.info");
console.groupEnd();

// Grupo del Mensaje console.warn
console.group("Grupo console warn");
	console.time("presentación console.warn");
	console.warn("%c Hola !!!, soy " + nombre, "background-color: crimson; color: black; font-size: 60px;");
console.timeEnd("presentación console.warn");
console.groupEnd();

```

**5 -** Crea una tabla usando la consola para mostrar el nombre de tus compañeros y el puesto que ocupa en la clase.

```javascript
var alumnos = [ { nombre: "Juan", puesto: 1 }, { nombre: "Oscar", puesto: 2 }, { nombre: "Paul", puesto: 3 }, { nombre: "Nuria", puesto: 4 }, { nombre: "Noemi", puesto: 5 }, { nombre: "Oliver", puesto: 6 }];
console.table(alumnos);

```


## Interacción Básica con el Usuario
### Ejercicios

**1 -** Vamos a solicitar la colaboración del usuario para lograr nuestros objetivos:
- Objetivos:
	-  Captura el nombre del usuario usando prompt
	-  Pregunta al usuario si desea *"comprobar lo rápido que funciona su navegador"*.
	-  En caso afirmativo imprimiremos el nombre del usuario por consola aplicandole estilos y calculando el tiempo que tarda en realizar la operación
    - En caso negativo mostraremos un *alert* informativo.

```javascript

var nombre = prompt("Bienvenido !!! , ¿dinos tu nombre");
var respuesta = confirm("¿Quieres comprobar lo rápido que funciona tu navegador?");

if (respuesta) {

  console.time("velocidad del navegador");
  console.info("%c Hola " + nombre, "background-color: green; font-size: 30px"); 
  console.timeEnd("velocidad del navegador");
}

else {
	alert(nombre + ", el navegador se destruirá en 5 segundos ... ");
}

```

## Operaciones
### Ejercicios

**1 -** Diseña un algoritmo que lea dos números y realice los siguientes cálculos:
- Valor de su suma
- Valor de su resta
- Valor de su division
- Valor de su producto

```javascript

function calcular(numero1, numero2) {

	var suma = numero1 + numero2;
    var resta= numero1 - numero2;
    var division = numero1 / numero2;
    var producto = numero1 * numero2;
 
    console.info ("El resultado de la suma es: " + suma);
    console.info ("El resultado de la resta es: " + resta);
    console.info ("El resultado de la división es: " + division);
    console.info ("El resultado del producto es: " + producto);
  
}

calcular(3,3);

```

**2 -** - Diseña un algoritmo para calcular el porcentaje de hombres y mujeres en nuestro curso.
- Trucos:
	- Calcular porcentajes (segmento*100)/total

```javascript

function porcentajes(hombres, mujeres) {
  
    var totalAlumnos = hombres + mujeres;
    var porcentajeMujeres = (mujeres/totalAlumnos)*100; 
    var porcentajeHombres = (hombres/totalAlumnos)*100; 
  
    console.info("El total de alumnos es " + totalAlumnos );
    console.info("El porcentaje de hombre es del " + porcentajeHombres + " %" );
    console.info("El porcentaje de mujeres es del " + porcentajeMujeres + " %" );
}

porcentajes(5,4);

```