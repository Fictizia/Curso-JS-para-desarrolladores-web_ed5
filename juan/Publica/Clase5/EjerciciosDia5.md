# Clase 5 Ejercicios
## Estructuras de Control: Sentencias
### Ejercicios


Realiza los siguientes ejercicios usando en cada uno los tres tipos de condicionales (If...else, Switch, operador ternario )

**1 -** Diseña un algoritmo que lea dos números y los compare. Como resultado esperamos que nos diga cual es mayor... o si son iguales.

- Usando *if...else*
```javascript

function compararNumeros(valor1, valor2) {
  
  if(valor1>valor2) {
  
    console.info("Valor 1 es mayor que Valor 2");
    
  } else if (valor1<valor2) {
  
     console.info("Valor 1 es menor que Valor 2");
    
  } else {
  	console.info("Valor 1 es igual que Valor 2");
  }

}

```

- Usando *Operador Ternario (?:)*
```javascript

function compararNumeros(valor1, valor2) {
 
  console.info( (valor1>valor2)? "Valor1 es mayor que Valor2" : 
               	(valor1<valor2)? "Valor 1 es menor que Valor 2": 
               	"Valor 1 es igual que Valor 2" ); 
  
}

```

- Usando *Switch*
```javascript

function compararNumeros(valor1, valor2) {
  
  switch (true) {
    case (valor1>valor2) :
      console.info("Valor1 es mayor que Valor2");
    	break;
    
    case (valor1<valor2) :
      console.info("Valor1 es menor que Valor2");
      break;
    
    default:
      console.info("Valor 1 es igual que Valor2");
  }
  
}

```

**2 -** Diseña un algoritmo que lea tres números distintos y nos diga cual de ellos es el mayor.

- Usando *if...else*
```javascript

function compararNumeros(valor1, valor2, valor3) {
  
  if( (valor1>valor2) && (valor1>valor3) ) {
  	
    console.info("Valor1 es el mayor");
  
  } else if( (valor2>valor1) && (valor2>valor3) ) {
   
    console.info("Valor2 es el mayor");
  
  } else {
  	
    console.info("Valor3 es el mayor");
 
  }
  
}

```

- Usando *Operador Ternario (?:)*
```javascript

function compararNumeros(valor1, valor2, valor3) {
  
  ((valor1>valor2) && (valor1>valor3))? console.info("Valor1 es el mayor")
  	: ((valor2>valor1) && (valor2>valor3))? console.info("Valor2 es el mayor")
  	: console.info("Valor3 es el mayor");
}

```

- Usando *Switch*
```javascript

function compararNumeros(valor1, valor2, valor3) {
  
  switch(true) {
  
    case ( valor1>valor2 && valor1>valor3 ) :
      
      console.info("Valor1 es el mayor");
      break;
    
    case ( valor2>valor1 && valor2>valor3 ) :
      console.info("Valor2 es el mayor");
      break;
      
    default :
      console.info("Valor3 es el mayor");
 
  }

}

```


**3 -** Diseña un algoritmo que siga el siguiente proceso:
- Si el primero es negativo, debe sumar los otros dos
- Sino multiplicará los tres numeros
- Mostrar el resultado final incluyendo una referencia a la operación realizada.

- Usando *if...else*
```javascript

function compararNumeros(valor1, valor2, valor3) {
  
  var suma = valor2+valor3;
  var producto = valor1*valor2*valor3;
  
  if (valor1<0) {
    console.log("El primer valor es negativo: " +valor1+ "\n Sumanos: " +suma);
  
  }
  
  else {
    console.log("El primer valor es positivo: " +valor1+ "\n Multiplicamos: " + producto);
  }

}


```

- Usando *Operador Ternario (?:)*
```javascript

function compararNumeros(valor1, valor2, valor3) {
  
  var suma = valor2+valor3;
  var producto = valor1*valor2*valor3;
  
  (valor1<0)? console.log("El primer valor es negativo: " +valor1+ "\n Sumanos: " +suma)
  	:console.log("El primer valor es positivo: " +valor1+ "\n Multiplicamos: " + producto);

}

```

- Usando *Switch*
```javascript

function compararNumeros(valor1, valor2, valor3) {
  
  var suma = valor2+valor3;
  var producto = valor1*valor2*valor3; 
  
  switch (true) {
  
    case (valor1<0) :
      console.log("El primer valor es negativo: " +valor1+ "\n Sumanos: " +suma);
      break;
    
    default:
  		console.log("El primer valor es positivo: " +valor1+ "\n Multiplicamos: " + producto);
  }
 
}

```

**4 -** Diseña un algoritmo que aplique al precio de un producto un descuento cuando se den las siguientes caracteristicas.
- Se aplica un 25% cuando:
	- Estamos en los meses de invierno
	- Y no es viernes o fin de semana.

- Usando *if...else*
```javascript

function descuento(dia, mes, precioProducto) {
 
  
  if ( ( mes === "diciembre" || mes ==="enero" || mes === "febrero") && (dia === "lunes" || dia === "martes" || dia === "miercoles"  || dia === "jueves" ) ) {
    
    var precioFinal= precioProducto * 0.75;
  	console.log("Tienes descuento. El precio del producto es " + precioFinal);
  
  }
  
  else {
    
    console.log("Lo sentimos, no hay descuento. El precio del producto es " + precioProducto);
  
  }    
  
}
	
```

- Usando *Operador Ternario (?:)*
```javascript
   
   function descuento(dia, mes, precioProducto) {
  
   ( ( mes === "diciembre" || mes ==="enero" || mes === "febrero") && (dia === "lunes" || dia === "martes" || dia === "miercoles"  || dia === "jueves" ) )? console.log("Tienes descuento. El precio del producto es " + precioProducto * 0.75 )
  		: console.log("Lo sentimos, no hay descuento. El precio del producto es " + precioProducto);
  
  
}

```

- Usando *Switch*
```javascript
   
   function descuento(dia, mes, precioProducto) {
  
  switch ( true ) {
  
    case ( mes === "diciembre" || mes ==="enero" || mes === "febrero") && (dia === "lunes" || dia === "martes" || dia === "miercoles"  || dia === "jueves" )  :
      var precioFinal= precioProducto * 0.75;
  		console.log("Tienes descuento. El precio del producto es " + precioFinal);
  		break;
      
    default : 
    	console.log("Lo sentimos, no hay descuento. El precio del producto es " + precioProducto);
  
  }
  
}

```

**5 -** Diseña un algoritmo que al introducir un numero nos diga si es positivo o negativo.

- Usando *if...else*
```javascript

function esNegativo(valor) {

  if ( valor < 0) {
  	console.log ("En número es negativo");
  }
  
  else {
  console.log ("En número es positivo");
  }

}
	
```

- Usando *Operador Ternario (?:)*
```javascript

function esNegativo(valor) {

  ( valor < 0)? console.log ("En número es negativo") : console.log ("En número es positivo");

}

```

- Usando *Switch*
```javascript
    
function esNegativo(valor) {
  
  switch ( true ) {
  
    case ( valor < 0) : 
      console.log ("En número es negativo");
      break;
      
    default :
       console.log ("En número es positivo");
  }

}
    
```


**6 -** Diseña un algoritmo que al introducir un número nos diga si es par o impar.

- Usando *if...else*
```javascript

function esPar (numero) {
  
  if ( numero %2 === 0 ){
    console.info(numero, " es par");
  } 
  
  else {
     console.info(numero, " es impar");
  }

}

```

- Usando *Operador Ternario (?:)*
```javascript

function esPar (numero) {
  
  ( numero %2 === 0 )? console.info(numero, " es par"): console.info(numero, " es impar");

}

```

- Usando *Switch*
```javascript
    
function esPar (numero) {
  
  switch ( true ) {
    case ( numero %2 === 0 ) :
      console.info(numero, " es par");
      break;
      
    default:
  		console.info(numero, " es impar");
  }
  
}

```


**7 -** Diseña un algoritmo que nos confirme si un [año es bisiesto](https://es.wikipedia.org/wiki/A%C3%B1o_bisiesto) o no.
- Caracteristicas de un año bisiesto:
	- Tiene que ser divisible entre 4
	- No tiene que ser divisible entre 100
	- Puede ser divisble entre 100 y entre 400

- Usando *if...else*
```javascript

function bisiesto ( anyo ) {

  if (anyo %4 === 0 && anyo %100 !== 0) {
  	console.log("El año " +anyo+ " es bisiesto");
  }
  
  else if (anyo % 400 === 0 && anyo % 100 === 0) {
  	console.log("El año " +anyo+ " es bisiesto");
  }
  
  else {
    console.log("El año " +anyo+ " NO es bisiesto");
  }

}
	
```

- Usando *Operador Ternario (?:)*
```javascript
    
function bisiesto ( anyo ) {

  (anyo %4 === 0 && anyo %100 !== 0)? console.log("El año " +anyo+ " es bisiesto")
  : (anyo % 400 === 0 && anyo % 100 === 0)? console.log("El año " +anyo+ " es bisiesto")
  : console.log("El año " +anyo+ " NO es bisiesto");
  
}

```

- Usando *Switch*
```javascript

function bisiesto ( anyo ) {
  
  switch ( true ) {
  	
    case (anyo %4 === 0 && anyo %100 !== 0) :
      console.log("El año " +anyo+ " es bisiesto");
      break;
      
    case (anyo % 400 === 0 && anyo % 100 === 0) :
      console.log("El año " +anyo+ " es bisiesto");
      break;
      
    default :
      console.log("El año " +anyo+ " NO es bisiesto");
  
  }

}

```