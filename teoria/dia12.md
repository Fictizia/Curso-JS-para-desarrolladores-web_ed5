# Clase 12

### IMPORTANTE

![Portada_M_Vidal](http://www.fictizia.com/assets/imgs/blog/articles/26/sketch-masterclass-Marcos-Vidal.jpg)

**[Masterclass de Marcos Vidal: "Diseñando interfaces con Sketch: Procesos, plugins y trucos"](http://www.fictizia.com/actualidad/sketch-masterclass-Marcos-Vidal)**
- En Fictizia, el sábado 16 de Abril a las 10:30

**Ejercicios**

1 - Realiza una pagina web que muestre la cuenta atrás para terminar el curso en días, horas, minutos y segundos.
Objetivos Adicionales:
- Además debería de seguir actualizando la cuenta atrás de manera dinámica.
- Los datos horarios siempre deben mostrarse con dos dígitos, añadiendo un cero a la izquierda cuando sea necesario.

Nota: Podría ser muy útil usar *setTimeout* para lanzar una función cada cierto tiempo.

- [Solucion](https://github.com/UlisesGascon/curso-js-web-developers-012016/blob/master/otros/cuenta-atras.html)

### Testing

**Estado actual:**

![testing_graph](http://ashleynolan.co.uk/assets/img/blog/tooling-survey/2015/q7.jpg)


**Objetivos:**
- Código que verifica el funcionamiento de otro código.
- Deben poder realizarse de manera automática.
- Cubrir mayor cantidad de código posible.
- Independientes entre si.
- Capaces de ejercutarse infinidad de veces.
- Pueden agruparse en Test Suites.
- Uso de colores y mensajes claros.

- Ejemplo:
```javascript
    // Función 
    function sumar (p1, p2){
      return p1 + p2;
    }
    
    // Test
    function testSumar(){
      if (sumar(1, 2) !== 3) {
        document.write('<p style="color: red;">sumar(1, 2) ERROR - No devuelve 3</\p>');
      } else {
        document.write('<p style="color: green;">sumar(1, 2) OK</p>');
      }
    
      if (sumar("2", 2) !== 4) {
        document.write('<p style="color: red;">sumar("2", 2) ERROR - No devuelve 4</p>');
      } else {
        document.write('<p style="color: green;">sumar("2", 2) OK</p>');
      }
    }
```

### Test Driven Development (TDD)

> Desarrollo guiado por pruebas de software, o Test-driven development (TDD) es una práctica de ingeniería de software que involucra otras dos prácticas: Escribir las pruebas primero (Test First Development) y Refactorización (Refactoring). Para escribir las pruebas generalmente se utilizan las pruebas unitarias (unit test en inglés). En primer lugar, se escribe una prueba y se verifica que las pruebas fallan. A continuación, se implementa el código que hace que la prueba pase satisfactoriamente y seguidamente se refactoriza el código escrito. El propósito del desarrollo guiado por pruebas es lograr un código limpio que funcione. La idea es que los requisitos sean traducidos a pruebas, de este modo, cuando las pruebas pasen se garantizará que el software cumple con los requisitos que se han establecido [Wikiwand](https://www.wikiwand.com/es/Desarrollo_guiado_por_pruebas)

- Primero los test
- Depués el código (Refactorización <-> Testing)
    - Ciclo de Vida:
        - Escribe los tests
        - Ejecuta los tests (Sin código, solo probando los propios tests)
        - Escribe el código suficiente para que pasen los tests.
        - Ejecuta los tests
        - Refactoriza
        - Repite


### Behavior Driven Development (BDD)

> En la Ingeniería de Software, behavior-driven development o desarrollo guiado por el comportamiento (DGC), es un proceso de desarrollo de software que surgió a partir del desarrollo guiado por pruebas (DGP). El desarrollo guiado por el comportamiento combina las técnicas generales y los principios del DGP, junto con ideas del diseño guiado por el dominio y el análisis y diseño orientado a objetos para proveer al desarrollo de software y a los equipos de administración, con herramientas compartidas y un proceso compartido de colaboración en el desarrollo de software.

> Aunque el DGC es esencialmente una idea sobre cómo el desarrollo de software debería ser administrado tanto por los intereses del negocio como por el entendimiento técnico, la práctica del DGC asume el uso de herramientas de software especializadas para asistir en el proceso de desarrollo. Aunque estas herramientas son comúnmente desarrolladas específicamente para su uso en proyectos de DGC, se pueden ver como formas especializadas de las herramientas que asisten en el DGP. Las herramientas sirven para agregar automatización para el lenguaje ubicuo (lenguaje estructurado alrededor del modelo de dominio, utilizado en el diseño guiado por el dominio para conectar actividades entre miembros del equipo), el cual es el tema central del DGC. [Wikiwand](http://www.wikiwand.com/es/Desarrollo_guiado_por_comportamiento)

- Orientado al comportamiento 
- Se comprueban que las funcionalidades cumplan lo que se espera de ellas

### Frameworks:

**[QUnit](https://api.qunitjs.com/)**
- [Documentación](https://api.qunitjs.com/) 
- Utilizado por jQuery 
```javascript
    // Función 
    function sumar (p1, p2){
      return p1 + p2;
    }
        
    // Test
    test("test de la funcion sumar(p1, p2)", function() {
      equal(sumar( 1, 2), 3, "1 + 2 = 3" );
      notEqual(sumar( "2", 2), "4", " 2(cadena) + 2 != 4(cadena) ");
    });
```

**[Mocha](https://mochajs.org/)**
- Muy popular
- En necesario incluir [Chai](http://chaijs.com/)
```javascript       
    // Función 
    function sumar (p1, p2){
      return p1 + p2;
    }
            
    // Test
    mocha.setup('bdd');
    var expect = chai.expect;
    var should = chai.should();
    describe("Test de la funcion sumar(p1, p2)", function() {
      it('1 + 2 = 3', function() {
        expect(sumar( 1, 2)).to.equal(3);
      });
            
      it('\"2\" + 2 != \"4\"', function() {
        expect(sumar( "2", 2)).not.equal("4");
      });
            
    });
            
    mocha.run()
```

### QUnit

**Preparando el entorno:**
```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>QUnit</title>
  <link rel="stylesheet" href="//code.jquery.com/qunit/qunit-1.20.0.css">
</head>
<body>
  <div id="qunit"></div>
  <div id="qunit-fixture"></div>
  <script src="//code.jquery.com/qunit/qunit-1.20.0.js"></script>
</body>
</html>
```
- [Demo](../otros/qunit.html)

**[API Doc](http://api.qunitjs.com/):**

- [Assert](http://api.qunitjs.com/category/assert/)
	- assert.async() *JUnit espera la finalización de una operación/es asíncrona/s*:
		- Un caso
		```javascript
			QUnit.test( "Probando una llamada asíncrona assert.async() test", function( assert ) {
			  var llamadaTermianda = assert.async();
			  setTimeout(function() {
			    assert.ok( true, "Unica llamada terminada.");
			    llamadaTermianda();
			  }, 500 );
			});
		```
		- Multiples casos
		```javascript
			QUnit.test( "Multiples llamadas asíncronas realizadas", function( assert ) {
			  assert.expect( 3 );
			  var llamadaTermianda = assert.async( 3 );
			 
			  setTimeout(function() {
			    assert.ok( true, "Primera llamada terminada." );
			    llamadaTermianda();
			  }, 7000 );
			 
			  setTimeout(function() {
			    assert.ok( true, "Segunda llamada terminada." );
			    llamadaTermianda();
			  }, 6000 );
			 
			  setTimeout(function() {
			    assert.ok( true, "Tercera llamada terminada." );
			    llamadaTermianda();
			  }, 5000 );
			});
		```
	- assert.deepEqual() *Comparación estrcita*:
	```javascript
		QUnit.test("testing equal()", function() {
			var a = {'nombre' : 'Luis'};
			var b = a;
			deepEqual(a, b, "el objeto a y el b son iguales");
			b = {'nombre' : 'Luis'};
			deepEqual(a, b, "el objeto a y el b son iguales");
		});	
	```
	- assert.equal() *Comparación no estricta*:
	```javascript
		QUnit.test("testing equal()", function() {
			equal(1, 1, "1 es 1");
			equal("1","1", "\"1\" es \"1\"");
			equal(1, "1", "1 es \"1\"");
			equal(1, true, "1 es true");
			equal(1, !false, "1 no es false");
			
			// (objetos)
			var a = {'nombre' : 'Luis'};
			var b = a;
			equal(a, b, "el objeto a y el b son iguales");
			b = {'nombre' : 'Luis'};
			equal(a, b, "el objeto a y el b son iguales");
		});	
	```
	- assert.expect() *Especifica el número de comparaciones*:
	```javascript
		QUnit.test( "Usando assert.expect() ", function( assert ) {
		  assert.expect( 2 );
		 
		  function calcular( x, operacion ) {
		    return operacion( x );
		  }
		 
		  var resultado = calcular( 2, function( x ) {
		    assert.ok( true, "calcular() llama a la función operacion." );
		    return x * x;
		  });
		 
		  assert.equal( resultado, 4, "2 al cuadrado es 4" );
		});
	```
	- assert.notDeepEqual() *Comparación desigual estrcita*:
	```javascript
	    QUnit.test("testing equal()", function() {
	        var a = {'nombre' : 'Luis'};
		var b = {'nombre' : 'Alberto'};
	        notDeepEqual(a, b, "el objeto a y el b no son iguales");
	    }); 
	```
	- assert.notEqual() *Comparación desigual no estrcita*:
	```javascript
	    QUnit.test("testing notEqual()", function() {
	        notEqual(true, false, "1 no es false");
	    }); 
	```
	- assert.notOk() *Comparación de un valor boleano (false)*:
	```javascript
		QUnit.test( "Testeando assert.notOk()", function( assert ) {
		  assert.notOk( false, "test false" );
		  assert.notOk( "", "test cadena vacía" );
		  assert.notOk( NaN, "test NaN" );
		  assert.notOk( null, "test null" );
		  assert.notOk( undefined, "test undefined" );
		  // Fallará desde aquí
		  assert.notOk( true, "test true" );
		  assert.notOk( 1, "test número 1 " );
		  assert.notOk( "algo", "Test cadena no vacía" );
		});	
	```
	- assert.notPropEqual() *Comparación de las propiedades de dos objetos (false)*:
	```javascript
		QUnit.test( "Testeando notPropEqual()", function( assert ) {
			var a = {'nombre' : 'Luis', 'valor' : 2};
			var b = {'nombre' : 'Luis', 'valor' : '2'};
			notPropEqual(a, b, "el objeto a y el b no son iguales");
		});	
	```
	- assert.notStrictEqual() *Comparación estricta (false)*:
	```javascript
		QUnit.test( "Testeando assert.notStrictEqual()", function( assert ) {
		  assert.notStrictEqual( 1, "1", "1 y '1' mismo valor, pero diferente tipo" );
		});
	```
	- assert.ok() *Comparación de un valor boleano (true)*:
	```javascript
	    QUnit.test( "Testeando assert.ok()", function( assert ) {
	      assert.ok( true, "test true" );
	      assert.ok( 1, "test número 1 " );
	      assert.ok( "algo", "Test cadena no vacía" );
	    }); 
	```
	- assert.propEqual() *Comparación de las propiedades de dos objetos (true)*:
	```javascript
		QUnit.test( "Testeando propEqual()", function( assert ) {
			var a = {'nombre' : 'Luis', 'valor' : 2};
			var b = a;
			propEqual(a, b, "el objeto a y el b son iguales");
			b = {'nombre' : 'Luis', 'valor' : '2'};
			propEqual(a, b, "el objeto a y el b son iguales");
		});	
	```

	- assert.strictEqual() *Comparación estricta (true)*:
	```javascript
		QUnit.test("Testeando equal()", function() {
			strictEqual(1, 1, "1 is 1");
			strictEqual("1","1", "\"1\" is \"1\"");
			strictEqual(1, "1", "1 is \"1\"");
			strictEqual(1, true, "1 is true");
			strictEqual(1, !false, "1 is not false");
		});	
	```


- [Callbacks](http://api.qunitjs.com/category/callbacks/)
	- QUnit.begin() *Dispara un callback cuando empieza el test suite*:
	```javascript
		QUnit.begin(function( details ) {
		  console.log( "Total de Tests:", details.totalTests );
		});	
	```
	- QUnit.done() *Dispara un callback cuando termina el test suite*:
	```javascript
		QUnit.done(function( details ) {
		  console.log( "Total: ", details.total, " Fallados: ", details.failed, " Pasados: ", details.passed, " Tiempo: ", details.runtime );
		});
	```
	- QUnit.log() *Dispara un callback cuando termina una comprobación*:
	```javascript
		QUnit.log(function( details ) {
		  console.log( "Log: ", details.result, details.message );
		});
	```
	- QUnit.moduleDone() *Dispara un callback cuando termina un módulo*:
	```javascript
		QUnit.moduleDone(function( details ) {
		  console.log( "Módulo terminado: ", details.name, "Fallos/Total: ", details.failed, details.total );
		});	
	```
	- QUnit.moduleStart() *Dispara un callback cuando empieza el módulo*:
	```javascript
		QUnit.moduleStart(function( details ) {
		  console.log( "Módulo empezado: ", details.name );
		});
	```
	- QUnit.testDone() *Dispara un callback cuando termina un test*:
	```javascript
		QUnit.testDone(function( details ) {
		  console.log( "Test terminado: ", details.module, details.name, "Fallados/total: ", details.failed, details.total, details.duration );
		});
	```
	- QUnit.testStart() *Dispara un callback cuando empieza un test*:
	```javascript
		QUnit.testStart(function( details ) {
		  console.log( "Ahora: ", details.module, details.name );
		});
	```


- [Test](http://api.qunitjs.com/category/test/)
	- QUnit.module() *Agrupar los tests bajo una misma etiqueta*:
		- Usando módulos:
		```javascript
			QUnit.module( "Módulo A", function(){
				QUnit.test( "Ejemplo básico", function( assert ) {
				  assert.ok( true, "Espero true..." );
				});
				QUnit.test( "Ejemplo básico 2", function( assert ) {
				  assert.ok( true, "Espero true..." );
				});
			});
			
			QUnit.module( "Módulo B", function(){
				QUnit.test( "Ejemplo básico 3", function( assert ) {
				  assert.ok( true, "Espero true..." );
				});
				QUnit.test( "Ejemplo básico 4", function( assert ) {
				  assert.ok( true, "Espero true..." );
				});
			});
		```
		- Usando sub-módulos:
		```javascript
			QUnit.module( "Módulo A", function(){
				QUnit.test( "Ejemplo básico", function( assert ) {
					assert.ok( true, "Espero true..." );
				});
				QUnit.test( "Ejemplo básico 2", function( assert ) {
					assert.ok( true, "Espero true..." );
				});
			});
			
			QUnit.module( "Módulo B", function(){
				QUnit.test( "Ejemplo básico 3", function( assert ) {
					assert.ok( true, "Espero true..." );
				});
				QUnit.test( "Ejemplo básico 4", function( assert ) {
					assert.ok( true, "Espero true..." );
				});
			
				QUnit.module( "Módulo B.1", function() {
				    QUnit.test( "Ejemplo básico 5", function( assert ) {
				      assert.ok( true, "Espero true..." );
				    });
				});
			});
		```

	- QUnit.only() *Bloque todos los tests y solamente .only() se ejecutará*:
	```javascript
		QUnit.module( "Módulo A", function(){
			QUnit.only( "Ejemplo básico", function( assert ) {
				assert.ok( true, "Espero true..." );
			});
			QUnit.test( "Ejemplo básico 2", function( assert ) {
				assert.ok( true, "Espero true..." );
			});
		});	
	```
	- QUnit.skip() *Salta el test*:
	```javascript
		QUnit.module( "Módulo A", function(){
			QUnit.test( "Ejemplo básico", function( assert ) {
				assert.ok( true, "Espero true..." );
			});
			QUnit.skip( "Ejemplo básico 2", function( assert ) {
				assert.ok( true, "Espero true..." );
			});
		});
	```


**[Plugins](https://qunitjs.com/plugins/):**
- [Ninja Theme](https://github.com/Krinkle/qunit-theme-ninja) 
- [Html](https://github.com/JamesMGreene/qunit-assert-html)


### Resumen:

**Comparaciones de Igualdad**:

- .equal() *Comparación NO estrcita ( x == y)*
- .ok() *Comprobación boleana estricta ( x == true)*
- .strictEqual() *Comparación estrcita ( x === y)*

- Especiales:
	- .deepEqual() *Comparación recursiva para Expresiones regulares, Objetos, Arrays, Fechas, Funciones...*
	- .propEqual() *Comprobación estricta de las propiedades de un objeto*


**Comparaciones de Desigualdad**:

- .notEqual() *Comparación NO estrcita (x != y)*
- .notOk() *Comprobación boleana NO estricta ( x == false)*
- .notStrictEqual() *Comparación estrcita ( x !== y)*

- Especiales:
	- .notDeepEqual() *Comparación recursiva para Expresiones regulares, Objetos, Arrays, Fechas, Funciones...*
	- .notPropEqual() *Comprobación estricta de las propiedades de un objeto*



**Ejercicios:**

Todos los ejercicios deben seguir el mismo proceso:
- Escribir las pruebas primero (Test First Development)
- Refactorización (Refactoring)

**1 -** Diseña un algoritmo que lea dos números y realice los siguientes cálculos:
- Características:
	- Valor de su suma
	- Valor de su resta
	- Valor de su division
	- Valor de su producto

- Pruebas necesarias:
	- Comprobar si ambos parámetros son números
	- Comprobar si uno o varios parámetros son cadenas

```javascript
	// Tests
	QUnit.module( "Módulo de calculosVarios(valor1, valor2)", function(){
		
		var condicion = {suma: 50, resta: -30, division: 0.25, multiplicacion: 400};
		var condicion2 = {suma: 30, resta: 50, division: -4, multiplicacion: -400};

	    QUnit.test( "calculosVarios(10, 40) con números", function( assert ) {
	        propEqual(condicion, calculosVarios(10, 40), "calculosVarios(10, 40) es igual a condicion");
	    	propEqual(condicion2, calculosVarios(40, -10), "calculosVarios(40, -10) es igual a condicion2");
	    });


	    QUnit.test( "calculosVarios(\"10\", \"40\") con cadenas", function( assert ) {
	        propEqual(condicion, calculosVarios("10", "40"), "calculosVarios(\"10\", \"40\") es igual a condicion");
	    	propEqual(condicion2, calculosVarios("40", "-10"), "calculosVarios(\"40\", \"-10\") es igual a condicion2");
	    });

    });

	// Código
	function calculosVarios(valor1, valor2){
		valor1 = parseFloat(valor1);
		valor2 = parseFloat(valor2);
		return {
			suma: valor1+valor2,
			resta: valor1-valor2,
			division: valor1/valor2 ,
			multiplicacion: valor1*valor2
		}
	}
```

**2 -** Diseña un algoritmo para calcular el porcentaje de hombres y mujeres en nuestro curso.
- Trucos:
	- Calcular porcentajes (segmento*100)/total

- Pruebas necesarias:
	- Comprobar si ambos parámetros son números
	- Comprobar si uno o varios parámetros son cadenas

```javascript
	// Tests
	QUnit.module( "Módulo de porcentajeAlumnos()", function(){
		
		var condicion = {totalAlumnos: 10, porcentajeMujeres: 80, porcentajeHombres: 20};
		var condicion2 = {totalAlumnos: 10, porcentajeMujeres: 40, porcentajeHombres: 60};

	    QUnit.test( "con números", function( assert ) {
	        propEqual(condicion, porcentajeAlumnos(2,8), "porcentajeAlumnos(2,8) es igual a la condición");
	    	propEqual(condicion2, porcentajeAlumnos(6,4), "porcentajeAlumnos(6,4) es igual a la condición2");
	    });

	    QUnit.test( "con cadenas", function( assert ) {
	        propEqual(condicion, porcentajeAlumnos("2", "8"), "porcentajeAlumnos(\"2\", \"8\") es igual a la condición");
	    	propEqual(condicion2, porcentajeAlumnos("6", "4"), "porcentajeAlumnos(\"6\", \"4\") es igual a la condición2");
	    });

    });

	// Código
	function porcentajeAlumnos(totalHombres, totalMujeres){
		totalHombres = parseFloat(totalHombres);
		totalMujeres = parseFloat(totalMujeres);
		totalAlumnos = totalHombres + totalMujeres;

		return {
			totalAlumnos: totalAlumnos,
			porcentajeMujeres: (totalMujeres*100)/totalAlumnos,
			porcentajeHombres: (totalHombres*100)/totalAlumnos
		}
	}
```


**3 -** Diseña un algoritmo que lea dos números y los compare. Como resultado esperamos que nos diga cual es mayor... o si son iguales.

- Pruebas necesarias:
	- Comprobar si ambos parámetros son números
	- Comprobar si uno o varios parámetros son cadenas

```javascript
	// Tests
	QUnit.module( "Módulo de compararNumeros()", function(){
		
		var condicion = "2 es mayor";
		var condicion2 = "Son iguales";

	    QUnit.test("con números", function() {
	        deepEqual(compararNumeros(1,2), condicion, "1 vs. 2 (es el mayor)");
	        deepEqual(compararNumeros(2,1), condicion, "1 vs. 2 (es el mayor)");
	        deepEqual(compararNumeros(1,1), condicion2, "1 y 1 son iguales");
	    }); 

	    QUnit.test("con cadenas", function() {
	        deepEqual(compararNumeros("1","2"), condicion, "\"1\" vs. \"2\" (es el mayor)");
	        deepEqual(compararNumeros("2","1"), condicion, "\"1\" vs. \"2\" (es el mayor)");
	        deepEqual(compararNumeros("1","1"), condicion2, "\"1\" y \"1\" son iguales");
	    }); 
    });

	// Código	
	function compararNumeros (valor1, valor2) {

		valor1 = parseFloat(valor1);
		valor2 = parseFloat(valor2);

		if (valor1 > valor2) {
		
			return valor1 + " es mayor";
		
		} else if (valor1 < valor2){
		
			return valor2 + " es mayor";
		
		} else {
		
			return "Son iguales";
		
		};
	}
```

**4 -** Diseña un algoritmo que lea tres números distintos y nos diga cual de ellos es el mayor.

- Pruebas necesarias:
	- Comprobar si ambos parámetros son números
	- Comprobar si uno o varios parámetros son cadenas
	- Comprueba si todos los parámetros son iguales

```javascript
	// Tests
	QUnit.module( "Módulo de compararVariosNumeros()", function(){
		
		var condicion = "3 es mayor";
		var condicion2 = "Son iguales";

	    QUnit.test("con números", function() {
	        deepEqual(compararVariosNumeros(2,1,3), condicion, "compararVariosNumeros(2,1,3) 3 es el mayor");
	        deepEqual(compararVariosNumeros(1,3,2), condicion, "compararVariosNumeros(1,3,2) 3 es el mayor");
	        deepEqual(compararVariosNumeros(3,2,1), condicion, "compararVariosNumeros(3,2,1) 3 es el mayor");
	        deepEqual(compararVariosNumeros(3,3,3), condicion2, "compararVariosNumeros(3,3,3) son iguales");
	    }); 

	    QUnit.test("con cadenas", function() {
	        deepEqual(compararVariosNumeros("2","1","3"), condicion, "compararVariosNumeros(\"2\",\"1\",\"3\") 3 es el mayor");
	        deepEqual(compararVariosNumeros("1","3","2"), condicion, "compararVariosNumeros(\"1\",\"3\",\"2\") 3 es el mayor");
	        deepEqual(compararVariosNumeros("3","2","1"), condicion, "compararVariosNumeros(\"3\",\"2\",\"1\") 3 es el mayor");
	        deepEqual(compararVariosNumeros("3","3","3"), condicion2, "compararVariosNumeros(\"3\",\"3\",\"3\") son iguales");
	    }); 
    });

	// Código
	function compararVariosNumeros (valor1, valor2, valor3) {

		valor1 = parseFloat(valor1);
		valor2 = parseFloat(valor2);
		valor3 = parseFloat(valor3);

		if (valor1 > valor2 & valor1 > valor3) {
			return valor1 + " es mayor";
		} else if (valor1 === valor2 && valor2 === valor3) {
			return "Son iguales";
		} else {
			if(valor2 > valor3){
				return valor2 + " es mayor";
			} else {
				return valor3 + " es mayor";
			}
		};
	}
```

**5 -** Diseña un algoritmo que siga el siguiente proceso:
- Características:
	- Pedir por teclado tres números.
	- Si el primero es negativo, debe sumar los otros dos
	- Sino multiplicará los tres numeros
	- Mostrar el resultado final incluyendo una referencia a la operación realizada.

- Pruebas necesarias:
	- Comprobar si ambos parámetros son números
	- Comprobar si uno o varios parámetros son cadenas

```javascript
	// Tests
	QUnit.module( "Módulo de jugandoConNumeros()", function(){
		
		var condicion = "El resutlado de la multiplicacion es 6";
		var condicion2 = "El resutlado de la multiplicacion es 27";
		var condicion3 = "El resultado de la suma es 5";

	    QUnit.test("con números", function() {
	        deepEqual(jugandoConNumeros(2,1,3), condicion, "2 x 1 x 3 = 6");
	        deepEqual(jugandoConNumeros(3,3,3), condicion2, "3 x 3 x 3 = 27");
	        deepEqual(jugandoConNumeros(-1,3,2), condicion3, "3 + 2 = 5");
	    }); 

	    QUnit.test("con cadenas", function() {
	        deepEqual(jugandoConNumeros("2","1","3"), condicion, "\"2\" x \"1\" x \"3\" = 6");
	        deepEqual(jugandoConNumeros("3","3","3"), condicion2, "\"3\" x \"3\" x \"3\" = 27");
	        deepEqual(jugandoConNumeros("-1","3","2"), condicion3, "\"3\" + \"2\" = 5");
	    }); 
    });

	// Código
	function jugandoConNumeros (valor1, valor2, valor3) {

		valor1 = parseFloat(valor1);
		valor2 = parseFloat(valor2);
		valor3 = parseFloat(valor3);

		if (valor1 < 0) {
			return "El resultado de la suma es " + (valor2 + valor3);
		} else {
			return "El resutlado de la multiplicacion es " + (valor1 * valor2 * valor3);
		};
	}
```


**6 -** Diseña un algoritmo que aplique al precio de un producto un descuento cuando se den las siguientes caracteristicas.
- Se aplica un 25% cuando:
	- Estamos en los meses de invierno
	- Y no es viernes o fin de semana.

- Pruebas necesarias:
	- Comprobar si uno o varios los parámetros son números
	- Comprobar si uno o varios parámetros son cadenas
	- Comprobar cada uno de los meses del invierno
	- Comprobar cada día de la semana
	- Comprobar precios negativos
	- Comprobar "diaSemana": "Sabado" y "Sábado"
	- Comprobar "diaSemana": "Sabado" y "Sábado"

```javascript
	// Tests
	QUnit.module( "Módulo de calcularDescuento()", function(){
		
		var condicion = "BINGO! Has acertado de mes y días. Debes pagar solamente 375";
		var condicion1 = "Precio incorrecto!";
		var condicion2 = "No se aplica descuento.. ven en invierno mejor!. Debes pagar 500";
		var condicion3 = "No se aplica descuento aunque sea invierno.. ven durante la semana mejor!. Debes pagar 500";


	    QUnit.test("Precios", function() {
	        deepEqual(calcularDescuento (1, 1, -500), condicion1, "-500");
	        deepEqual(calcularDescuento (1, 1, 0), condicion1, "0");
	        deepEqual(calcularDescuento (1, 1, 500), condicion, "500");
	        deepEqual(calcularDescuento (1, 1, "500"), condicion, "\"500\"");
	    }); 

	    QUnit.test("Días de la semana", function() {
	        deepEqual(calcularDescuento (1, 1, 500), condicion, "(1) - Lunes");
	        deepEqual(calcularDescuento (1, "1", 500), condicion, "(\"1\") - Lunes");
	        deepEqual(calcularDescuento (1, "Lunes", 500), condicion, "(\"Lunes\") - Lunes");
	        deepEqual(calcularDescuento (1, 2, 500), condicion, "(2) - Martes");
	        deepEqual(calcularDescuento (1, "2", 500), condicion, "(\"2\") - Martes");
	        deepEqual(calcularDescuento (1, "Martes", 500), condicion, "(\"Martes\") - Martes");
	        deepEqual(calcularDescuento (1, 3, 500), condicion, "(3) - Miércoles");
			deepEqual(calcularDescuento (1, "3", 500), condicion, "(\"3\") - Miércoles");
			deepEqual(calcularDescuento (1, "Miercoles", 500), condicion, "(\"Miercoles\") - Miércoles");
	        deepEqual(calcularDescuento (1, 4, 500), condicion, "(4) - Jueves");
			deepEqual(calcularDescuento (1, "4", 500), condicion, "(\"4\") - Jueves");
			deepEqual(calcularDescuento (1, "Jueves", 500), condicion, "(\"Jueves\") - Jueves");
	        deepEqual(calcularDescuento (1, 5, 500), condicion3, "(5) - Viernes");
			deepEqual(calcularDescuento (1, "5", 500), condicion3, "(\"5\") - Viernes");
			deepEqual(calcularDescuento (1, "Viernes", 500), condicion3, "(\"Viernes\") - Viernes");
	        deepEqual(calcularDescuento (1, 6, 500), condicion3, "(6) - Sábado");
	        deepEqual(calcularDescuento (1, "6", 500), condicion3, "(\"6\") - Sábado");
	        deepEqual(calcularDescuento (1, "Sabado", 500), condicion3, "(\"Sabado\") - Sábado");
	        deepEqual(calcularDescuento (1, "Sábado", 500), condicion3, "(\"Sábado\") - Sábado");
	        deepEqual(calcularDescuento (1, 7, 500), condicion3, "(7) - Domingo");
			deepEqual(calcularDescuento (1, "7", 500), condicion3, "(\"7\") - Domingo");
			deepEqual(calcularDescuento (1, "Domingo", 500), condicion3, "(\"Domingo\") - Domingo");
	    });

		QUnit.test("Meses del año", function() {
	        deepEqual(calcularDescuento (1, 1, 500), condicion, "(1) - Enero");
	        deepEqual(calcularDescuento ("1", 1, 500), condicion, "(\"1\") - Enero");
	        deepEqual(calcularDescuento ("Enero", 1, 500), condicion, "(\"Enero\") - Enero");
	        deepEqual(calcularDescuento (2, 1, 500), condicion, "(2) - Febrero");
	        deepEqual(calcularDescuento ("2", 1, 500), condicion, "(\"2\") - Febrero");
	        deepEqual(calcularDescuento ("Febrero", 1, 500), condicion, "(\"Febrero\") - Febrero");
	        deepEqual(calcularDescuento (3, 1, 500), condicion2, "(3) - Marzo");
	        deepEqual(calcularDescuento ("3", 1, 500), condicion2, "(\"3\") - Marzo");
	        deepEqual(calcularDescuento ("Marzo", 1, 500), condicion2, "(\"Marzo\") - Marzo");	        
	        deepEqual(calcularDescuento (4, 1, 500), condicion2, "(4) - Abril");
	        deepEqual(calcularDescuento ("4", 1, 500), condicion2, "(\"4\") - Abril");
	        deepEqual(calcularDescuento ("Abril", 1, 500), condicion2, "(\"Abril\") - Abril");
	        deepEqual(calcularDescuento (5, 1, 500), condicion2, "(5) - Mayo");
	        deepEqual(calcularDescuento ("5", 1, 500), condicion2, "(\"5\") - Mayo");
	        deepEqual(calcularDescuento ("Mayo", 1, 500), condicion2, "(\"Mayo\") - Mayo");
	        deepEqual(calcularDescuento (6, 1, 500), condicion2, "(6) - Junio");
	        deepEqual(calcularDescuento ("6", 1, 500), condicion2, "(\"6\") - Junio");
	        deepEqual(calcularDescuento ("Junio", 1, 500), condicion2, "(\"Junio\") - Junio");
	        deepEqual(calcularDescuento (7, 1, 500), condicion2, "(7) - Julio");
	        deepEqual(calcularDescuento ("7", 1, 500), condicion2, "(\"7\") - Julio");
	        deepEqual(calcularDescuento ("Julio", 1, 500), condicion2, "(\"Julio\") - Julio");
	        deepEqual(calcularDescuento (8, 1, 500), condicion2, "(8) - Agosto");
	        deepEqual(calcularDescuento ("8", 1, 500), condicion2, "(\"8\") - Agosto");
	        deepEqual(calcularDescuento ("Agosto", 1, 500), condicion2, "(\"Agosto\") - Agosto");
	        deepEqual(calcularDescuento (9, 1, 500), condicion2, "(9) - Septiembre");
	        deepEqual(calcularDescuento ("9", 1, 500), condicion2, "(\"9\") - Septiembre");
	        deepEqual(calcularDescuento ("Septiembre", 1, 500), condicion2, "(\"Septiembre\") - Septiembre");
	        deepEqual(calcularDescuento (10, 1, 500), condicion2, "(10) - Octubre");
	        deepEqual(calcularDescuento ("10", 1, 500), condicion2, "(\"10\") - Octubre");
	        deepEqual(calcularDescuento ("Octubre", 1, 500), condicion2, "(\"Octubre\") - Octubre");
	        deepEqual(calcularDescuento (11, 1, 500), condicion2, "(11) - Noviembre");
	        deepEqual(calcularDescuento ("11", 1, 500), condicion2, "(\"11\") - Noviembre");
	        deepEqual(calcularDescuento ("Noviembre", 1, 500), condicion2, "(\"Noviembre\") - Noviembre");
	        deepEqual(calcularDescuento (12, 1, 500), condicion, "(12) - Diciembre");
	        deepEqual(calcularDescuento ("12", 1, 500), condicion, "(\"12\") - Diciembre");
	        deepEqual(calcularDescuento ("Diciembre", 1, 500), condicion, "(\"Diciembre\") - Diciembre");
		});

    });

	// Código
	function calcularDescuento (mes, diaSemana, precio) {

		
		if (typeof mes === 'string'){
			
			switch (mes){
				case '12':
					mes = "Diciembre";
					break;
				case '1':
					mes = "Enero";
					break;
				case '2':
					mes = "Febrero";
					break;
			}
		} else {
			mes = parseInt(mes);
			
			switch (mes){
				case 12:
					mes = "Diciembre";
					break;
				case 1:
					mes = "Enero";
					break;
				case 2:
					mes = "Febrero";
					break;
			}
		}

		if (typeof diaSemana === 'string'){

			switch (diaSemana){
				case '5':
					diaSemana = "Viernes";
					break;
				case '6':
					diaSemana = "Sabado";
					break;
				case '7':
					diaSemana = "Domingo";
					break;
			}
		} else {
			
			diaSemana = parseInt(diaSemana);
			
			switch (diaSemana){
				case 5:
					diaSemana = "Viernes";
					break;
				case 6:
					diaSemana = "Sabado";
					break;
				case 7:
					diaSemana = "Domingo";
					break;
			}

		}

		
		precio = parseFloat(precio);

		var descuento = 25*precio/100;
		var precioConDescuento = precio - descuento;
		
		if (precio > 0){
			if (mes === "Diciembre" || mes === "Enero" || mes === "Febrero") {
				
				if(diaSemana === "Viernes" || diaSemana === "Sabado" || diaSemana === "Sábado" || diaSemana === "Domingo"){
					return "No se aplica descuento aunque sea invierno.. ven durante la semana mejor!. Debes pagar " + precio;
				} else {
					return "BINGO! Has acertado de mes y días. Debes pagar solamente " + precioConDescuento;
				}

			} else {
				return "No se aplica descuento.. ven en invierno mejor!. Debes pagar " + precio;
			}
		
		} else {
			return "Precio incorrecto!";
		}

	}
```


**7 -** Diseña un algoritmo que al introducir un numero por teclado. Que nos diga si es positivo o negativo.
- Pruebas necesarias:
	- numeros, cadenas, null, undefined, etc...

```javascript
	// Tests
	QUnit.module( "Módulo de esPositivo()", function(){

	    QUnit.test("Multiples tipos", function() {
	    	notOk(esPositivo(-1), "-1" );
	      	notOk(esPositivo("-1"), "\"-1\"");
	      	ok(esPositivo(1), "1");
	      	ok(esPositivo("1"), "\"1\"");
	      	ok(esPositivo(), "Vacio");
	      	ok(esPositivo(""), "Cadena vacia");
	      	ok(esPositivo(undefined), "undefined");
	      	ok(esPositivo(null), "null");
	      	ok(esPositivo(NaN), "NaN");
	    }); 

    });

	// Código
	function esPositivo(numero) {
		
		numero = parseFloat(numero);
		
		if(numero < 0){
			return false;
		} else {
			return true;
		}

	}
```

**8 -** Diseña un algoritmo que al introducir un número por teclado. Que nos diga si es par o impar.

- Pruebas necesarias:
	- numeros, cadenas, null, undefined, etc...

```javascript
	// Tests
	QUnit.module( "Módulo de esPar()", function(){

	    QUnit.test("Multiples tipos", function() {
	      	ok(esPar(2), "2");
	      	ok(esPar("2"), "\"2\"");
	      	ok(esPar(-2), "-2");
	      	ok(esPar("-2"), "\"-2\"");
	    	notOk(esPar(1), "1" );
	      	notOk(esPar("1"), "\"1\"");
	    	notOk(esPar(-1), "-1" );
	      	notOk(esPar("-1"), "\"-1\"");	   
	      	notOk(esPar(), "Vacío (sin parámetros)");
	      	notOk(esPar(""), "Cadena vacia");
	      	notOk(esPar(undefined), "undefined");
	      	notOk(esPar(null), "null");
	      	notOk(esPar(NaN), "NaN");
	    }); 

    });

	// Código
	function esPar(numero) {
		
		numero = parseFloat(numero);
		
		if(numero %2 === 0 ){
			return true;
		} else {
			return false;
		}

	}
```

**9 -**  Diseña un algoritmo para identificar a los clientes autorizados a entrar a nuestro sistema.
- Características:
	- La palabra clave es "Fictizia mola mucho".
	- Devuelve true si se acierta.
	- Devuelve false si no se acierta.

```javascript
	// Tests
	QUnit.module( "Módulo de eureka()", function(){
		
		QUnit.config.reorder = false;
	    
	    QUnit.test("intentos...", function() {
	    	ok(eureka("Fictizia mola mucho"), "pass: \"Fictizia mola mucho\"");
	    	notOk(eureka("hola"), "pass: \"hola\"");
	      	notOk(eureka(true), "pass: true");
	    	notOk(eureka(-1), "pass: -1" );
	    }); 

    });

	// Código
	var contador = 0;
	function eureka (secreto) {
		var clave = "Fictizia mola mucho";
			
			if (secreto === clave) {

				return true;
			
			} else {

				return false;
			}
	}
```

**10 -** Diseña un algoritmo que confirme si una fecha es valida y además devuelva la fecha en dos formatos diferentes.
- Características:
	- El usuario introduce tres números (día, mes, año)
	- Validar la fecha. En caso de error incluir un mensaje informativo.
	- El año mínimo es 1970
	- Después de validar, devolvemos la fecha en formato DD/MM/AAAA
	- Convertimos el número del mes, en el nombre del mes real y devolvemos la fecha en el siguiente formato ( DIASEMANA, DD de MES de AAAA)

```javascript
	// Tests
	QUnit.module( "Módulo de verificadorDeFechas()", function(){
		
		var condicion = "Error! los datos no son correctos!";
		var condicion2 = {fecha: "24/03/2016", fechaCompleta: "jueves, 24 de marzo de 2016"};
	    
	    QUnit.test("Entrada de datos", function() {
			deepEqual(verificadorDeFechas(24,3,2016), condicion2, "(24/03/2016) Fecha completa");
			deepEqual(verificadorDeFechas("24","3","2016"), condicion2, "(24/03/2016) Fecha completa (string)");
	    	deepEqual(verificadorDeFechas(-1, 1, 1980), condicion, "(-1) Día fuera de rango");
	    	deepEqual(verificadorDeFechas(32, 1, 1980), condicion, "(32) Día fuera de rango");
	    	deepEqual(verificadorDeFechas("hola", 1, 1980), condicion, "(\"hola\") Día no válido");
	    	deepEqual(verificadorDeFechas(1, -1, 1980), condicion, "(-1) Mes fuera de rango");
	    	deepEqual(verificadorDeFechas(1, 13, 1980), condicion, "(13) Mes fuera de rango");
	    	deepEqual(verificadorDeFechas(1, "hola", 1980), condicion, "(\"hola\") Mes no válido");
	    	deepEqual(verificadorDeFechas(1, 1, 1969), condicion, "(1969) Mes fuera de rango");
	    	deepEqual(verificadorDeFechas(1, 1, "hola"), condicion, "(\"hola\") Mes no válido");
	    }); 

    });

	// Código
	function verificadorDeFechas(day, month, year) {
		
		day = parseInt(day);
		month = parseInt(month);
		year = parseInt(year);

		if(day <= 31 && day > 0 && month <=12 && month > 0 && year >= 1970){

			// https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date
			var fecha = new Date(year, month-1, day);

			var opciones = { 
				weekday: 'long', 
				year: 'numeric', 
				month: 'long', 
				day: 'numeric' 
			};

			return {
				fecha: fecha.toLocaleDateString('es-ES'),
				fechaCompleta: fecha.toLocaleDateString('es-ES', opciones)
			}

		} else {
			return "Error! los datos no son correctos!"
		}

	}
```

**11 -** Diseña un algoritmo que nos confirme si un [año es bisiesto](https://es.wikipedia.org/wiki/A%C3%B1o_bisiesto) o no.
- Caracteristicas de un año bisiesto:
	- Tiene que ser divisible entre 4
	- No tiene que ser divisible entre 100
	- Puede ser divisble entre 100 y entre 400

```javascript
	// Tests
	QUnit.module( "Módulo de esBisiesto()", function(){

	    QUnit.test("Entrada de datos", function() {
	    	ok(esBisiesto("-4"), "(\"-4\") es bisiesto");
	    	ok(esBisiesto(1904), "(1904) es bisiesto");
	    	notOk(esBisiesto(), "() parámetro vacío");
	    	notOk(esBisiesto(-1), "(-1) NO es bisiesto");
	    	notOk(esBisiesto("1905"), "(\"1905\") NO es bisiesto");
	    }); 

    });

	// Código
	function esBisiesto(year) {
		
		year = parseInt(year);

		if ((year % 4 === 0 && year % 100 !== 0) || (year % 400 === 0 & year % 100 === 0)) {
			
			return true;
		
		} else {
			
			return false;
		
		};
```

**12 -** Diseña un algoritmo que imprima los numeros del 1 al 100.

```javascript
	// Tests
	QUnit.module( "Módulo de contadorPositivo()", function(){

		var condicion = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98, 99, 100];

	    QUnit.test("Verificar resultados", function() {
	    	deepEqual(contadorPositivo(), condicion, "Array [1-100]");
	    }); 

    });

	// Código
	function contadorPositivo() {
		
		var cuenta = []

		for (var i = 1; i <= 100; i++) {
			cuenta.push(i);
		};

		return cuenta;

	}
```


**13 -** Diseña un algoritmo que imprima los numeros del 100 al 0.

```javascript
	// Tests
	QUnit.module( "Módulo de contadorNegativo()", function(){

		var condicion = [100, 99, 98, 97, 96, 95, 94, 93, 92, 91, 90, 89, 88, 87, 86, 85, 84, 83, 82, 81, 80, 79, 78, 77, 76, 75, 74, 73, 72, 71, 70, 69, 68, 67, 66, 65, 64, 63, 62, 61, 60, 59, 58, 57, 56, 55, 54, 53, 52, 51, 50, 49, 48, 47, 46, 45, 44, 43, 42, 41, 40, 39, 38, 37, 36, 35, 34, 33, 32, 31, 30, 29, 28, 27, 26, 25, 24, 23, 22, 21, 20, 19, 18, 17, 16, 15, 14, 13, 12, 11, 10, 9, 8, 7, 6, 5, 4, 3, 2, 1, 0];

	    QUnit.test("Verificar resultados", function() {
	    	deepEqual(contadorNegativo(), condicion, "Array [100-0]");
	    }); 

    });

	// Código
	function contadorNegativo() {
		
		var cuenta = [];

		for (var i = 100; i >= 0; i--) {
			cuenta.push(i);
		};

		return cuenta;

	}
```


**14 -** Diseña un algoritmo que imprima los numeros pares entre 0 y 100.

```javascript
	// Tests
	QUnit.module( "Módulo de contadorPares()", function(){

		var condicion = [0, 2, 4, 6, 8, 10, 12, 14, 16, 18, 20, 22, 24, 26, 28, 30, 32, 34, 36, 38, 40, 42, 44, 46, 48, 50, 52, 54, 56, 58, 60, 62, 64, 66, 68, 70, 72, 74, 76, 78, 80, 82, 84, 86, 88, 90, 92, 94, 96, 98, 100];

	    QUnit.test("Verificar resultados", function() {
	    	deepEqual(contadorPares(), condicion, "Array [0-100 (Pares)]");
	    }); 

    });

	// Código
	function contadorPares() {
		
		var cuenta = [];

		for (var i = 0; i <= 100; i += 2) {
			cuenta.push(i);
		};

		return cuenta;

	}
```

**15 -** Diseña un algoritmo que imprima los números impares entre un número dado por el usuario y los siguientes 50 números.

- Pruebas necesarias:
	- Números negativos, decimales, etc..
	- Cadenas

```javascript
	// Tests
	QUnit.module( "Módulo de contador50Impares()", function(){

		var condicion = [-5, -3, -1, 1, 3, 5, 7, 9, 11, 13, 15, 17, 19, 21, 23, 25, 27, 29, 31, 33, 35, 37, 39, 41, 43];
		var condicion2 = [7, 9, 11, 13, 15, 17, 19, 21, 23, 25, 27, 29, 31, 33, 35, 37, 39, 41, 43, 45, 47, 49, 51, 53, 55];

	    QUnit.test("Verificar resultados", function() {
	    	deepEqual(contador50Impares(-5.6), condicion, "Array [-5.6 -> (n50) (Impares)]");
	    	deepEqual(contador50Impares(-5), condicion, "Array [-5 -> (n50) (Impares)]");
	    	deepEqual(contador50Impares("-5"), condicion, "Array [\"-5\" -> (n50) (Impares)]");
	    	deepEqual(contador50Impares(6), condicion2, "Array [6 -> (n50) (Impares)]");
	    	deepEqual(contador50Impares(6.6), condicion2, "Array [6.6 -> (n50) (Impares)]");
	    	deepEqual(contador50Impares("6"), condicion2, "Array [\"6\" -> (n50) (Impares)]");
	    }); 

    });

	// Código
	
	function contador50Impares (numero) {
		
		var cuenta = [];
		numero = parseInt(numero);

		for (var i = 1; i <= 50; i++) {
			
			if (numero % 2 !== 0){
				cuenta.push(numero);
				numero++
			} else {
				numero++
			}
			
		};

		return cuenta;

	}
```


**16 -** Diseña un algoritmo que imprima la suma de los 50 primeros numeros pares y el total de números impares partiendo de un número dado por el usuario

```javascript
	// Tests
	QUnit.module( "Módulo de contadorEspecial()", function(){

		var condicion = {totalImpares: 475, totalPares: 500};
		var condicion2 = {totalImpares: 775, totalPares: 750};

	    QUnit.test("Verificar resultados", function() {
	    	deepEqual(contadorEspecial(-5.6), condicion, "(-5.6) -> Objeto {totalPares, totalImpares}");
	    	deepEqual(contadorEspecial(-5), condicion, "(-5) -> Objeto {totalPares, totalImpares}");
	    	deepEqual(contadorEspecial("-5"), condicion, "(\"-5\") -> Objeto {totalPares, totalImpares}");
	    	deepEqual(contadorEspecial(6.6), condicion2, "(6.6) -> Objeto {totalPares, totalImpares}");
	    	deepEqual(contadorEspecial(6), condicion2, "(6) -> Objeto {totalPares, totalImpares}");
	    	deepEqual(contadorEspecial("6"), condicion2, "(\"6\") -> Objeto {totalPares, totalImpares}");
	    }); 

    });

	// Código
	
	function contadorEspecial (numero) {
		
		var totalImpares = 0;
		var totalPares = 0;
		numero = parseInt(numero);

		for (var i = 1; i <= 50; i++) {
			
			if (numero % 2 !== 0){
				totalImpares += numero;
				numero++;
			} else {
				totalPares += numero;
				numero++;
			}
			
		};

		return {
			totalImpares: totalImpares,
			totalPares: totalPares
		}
	}
```


**17 -** Diseña un algoritmo que cuente las veces que aparece una determinada letra en una frase que introduciremos por teclado.

```javascript
	// Tests
	QUnit.module( "Módulo de cuantasVeces()", function(){

	    QUnit.test("Verificar resultados", function() {
	    	deepEqual(cuantasVeces("a", "amigas, amigos, y demas... gentes"), 4, "(a) 4 veces en \"amigas, amigos, y demas... gentes\"");
	    	deepEqual(cuantasVeces("x", "amigas, amigos, y demas... gentes"), 0, "(x) 0 veces en \"amigas, amigos, y demas... gentes\"");
	    	notOk(cuantasVeces(), "false, sin parámetros");
	    	notOk(cuantasVeces(1, 1123), "false, usando números");
	    	notOk(cuantasVeces({letra:"a"}, {texto:"hola"}), "false, usando objetos");
	    }); 

    });

	// Código
	
	function cuantasVeces(letra, texto) {
		
		if (typeof letra === 'string' && typeof texto === 'string') {
			
			var totalVeces = 0;
			var seleccionTexto = texto.split("");
			
			for (var i = 0; i <= seleccionTexto.length; i++) {
				
				if (seleccionTexto[i] === letra){
					totalVeces++
				};
				
			};

			return totalVeces;

		} else {
			return false;
		}
	}
```

**18 -** Diseña un algoritmo introducido un numero y pasarlo a número romanos.
- Esperamos que el número sea menor de 50

![numeros_romanos](https://eloviparo.files.wordpress.com/2009/09/numeros-romans.jpg?w=466&h=172)

```javascript
	// Tests
	QUnit.module( "Módulo de conversionRomana()", function(){

	    QUnit.test("Verificar números", function() {
			deepEqual(conversionRomana(1), "I", "1 = I");
			deepEqual(conversionRomana(4), "IV", "4 = IV");
			deepEqual(conversionRomana(5), "V", "5 = V");
			deepEqual(conversionRomana(6), "VI", "6 = VI");
			deepEqual(conversionRomana(7), "VII", "7 = VII");
			deepEqual(conversionRomana(8), "VIII", "8 = VIII");
			deepEqual(conversionRomana(9), "IX", "9 = IX");
			deepEqual(conversionRomana(10), "X", "10 = X");
			deepEqual(conversionRomana(12), "XII", "12 = XII");
			deepEqual(conversionRomana(23), "XXIII", "23 = XXIII");
			deepEqual(conversionRomana(34), "XXXIV", "23 = XXIII");
			deepEqual(conversionRomana(45), "XLV", "45 = XLV");
			deepEqual(conversionRomana(50), "L", "50 = L");
	    }); 

	    QUnit.test("Verificar cadenas", function() {
			deepEqual(conversionRomana("1"), "I", "\"1\" = I");
			deepEqual(conversionRomana("4"), "IV", "\"4\" = IV");
			deepEqual(conversionRomana("5"), "V", "\"5\" = V");
			deepEqual(conversionRomana("6"), "VI", "\"6\" = VI");
			deepEqual(conversionRomana("7"), "VII", "\"7\" = VII");
			deepEqual(conversionRomana("8"), "VIII", "\"8\" = VIII");
			deepEqual(conversionRomana("9"), "IX", "\"9\" = IX");
			deepEqual(conversionRomana("10"), "X", "\"10\" = X");
			deepEqual(conversionRomana("12"), "XII", "\"12\" = XII");
			deepEqual(conversionRomana("23"), "XXIII", "\"23\" = XXIII");
			deepEqual(conversionRomana("34"), "XXXIV", "\"23\" = XXIII");
			deepEqual(conversionRomana("45"), "XLV", "\"45\" = XLV");
			deepEqual(conversionRomana("50"), "L", "\"50\" = L");
	    });

	    QUnit.test("Verificar otros", function() {
			notOk(conversionRomana(51), "51 - fuera de rango");
			notOk(conversionRomana(-1), "-1 - fuera de rango");
	    }); 
    });

	// Código
	
	function conversionRomana(numero) {
		
		numero = parseInt(numero);

		var numeroOriginal = numero;
	  

		if (numero <= 50 && numero > 0){

	    var numeroRomano = "";
	    
			while(numero > 0){
				
				if(numero === 50){
					numeroRomano = "L";
					numero = 0;
				} else if (numero >= 40 && numero < 50){
					numeroRomano += "XL";
					numero -= 40;
				} else if (numero >= 10 && numero < 40){
					numeroRomano += "X";
					numero -= 10;
				} else if(numero === 9){
					numeroRomano += "IX";
					numero -= 9;
				} else if(numero === 8){
					numeroRomano += "VIII";
					numero -= 8;
				} else if (numero === 7){
					numeroRomano += "VII";
					numero -= 7;
				} else if (numero === 6){
					numeroRomano += "VI";
					numero -= 6;
				} else if (numero === 5) {
					numeroRomano += "V";
					numero -= 5;
				} else if (numero === 4){
					numeroRomano += "IV";
					numero -= 4;				
				} else if(numero <= 3 && numero > 0){
					numeroRomano += "I";
					numero -= 1;
				}
	      
			}

			return numeroRomano;

		} else {
	    
			return false;
		
	  }

	}
```

**19 -** Agrupa todo el código y los test:
- Requisitos: 
	- Utiliza una estructura de archivos acorde
	- Utiliza el ninja theme.

- [Solución](otros/test_completo.html)

