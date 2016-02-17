# Clase 6 Ejercicios
## Bucles

**Ejercicios:**

Realiza los siguientes ejercicios usando en cada uno los tres tipos de bucles (Do...While, For, While )

**1 -**  Diseña un algoritmo para identificar a los clientes autorizados a entrar a nuestro sistema.
- Características:
	- La palabra clave es "Fictizia mola mucho"
	- Solo existen tres intentos
	- Si se pasan los tres intentos. Se despliega un mensaje informativo.

- Usando *for*
```javascript

var tuClave;
var clave = "Fictizia mola mucho";

for ( var i=3; i>=1; i-- ) {
  
   tuClave = prompt("¿Introduce la clave?");
  
   if(clave===tuClave) {
  
    console.info("Bienvenido !!!");
    break;
   }
  
  else {
    var intentos = i-1;
    console.info("Te quedan " + intentos + " intentos !!!");
  }

}


(clave===tuClave)? alert("Bienvenido !!!"): alert("Acceso denegado al sistema !!!! ");




```

- Usando *while*
```javascript
   
var tuClave;
var clave = "Fictizia mola mucho"; 
var intentos = 3;



while (intentos>=1) {
  
  tuClave = prompt("¿Introduce la clave?")

  if(clave===tuClave) {
  
    console.info("Bienvenido !!!");
    break;
  
  }
  
  else {
    intentos--;
    alert("Te quedan " + intentos + " intentos !!!");
 
  }
  
}


(clave===tuClave)? alert("Bienvenido !!!"): alert("Acceso denegado al sistema !!!! ");


```

- Usando *Do...While*
```javascript

var tuClave;
var clave = "Fictizia mola mucho";
var intentos = 3;


do {
  
  
  tuClave = prompt("Introduce la clave: ");
  
  if (tuClave === clave) {
  
    console.info("Bienvenido !!!");
    break;
  
  }
  
  else {
  	intentos--;
    console.info("Te quedan " + intentos + " intentos");
    
  }



} while (intentos>=1);


(clave===tuClave)? alert("Bienvenido !!!"): alert("Acceso denegado al sistema !!!! ");

```


**2 -** Diseña un algoritmo que imprima los numeros del 1 al 100.

- Usando *for*
```javascript
    
for ( var i=1 ; i<=100; i++ ) {

	console.info(i);

}
    
```

- Usando *while*
```javascript

var contador = 1;

while (contador<=100) {

  console.log(contador);
  contador++;

}

```

- Usando *Do...While*
```javascript

var contador = 1;

do {

  console.log(contador);
  contador++;

} while(contador<=100)

```

**3 -** Diseña un algoritmo que imprima los numeros del 100 al 0.

- Usando *for*
```javascript

for (var i=100 ; i>=0; i-- ) {

	console.info(i);

}

```

- Usando *while*
```javascript

var contador = 100;

while (contador>=0) {

  console.log(contador);
  contador--;

}

```

- Usando *Do...While*
```javascript

var contador = 100;

do {

  console.log(contador);
  contador--;

} while(contador>=0)

```


**4 -** Diseña un algoritmo que imprima los numeros pares entre 0 y 100.

- Usando *for*
```javascript
 
 for ( var contador= 0; contador<=100 ; contador++ ) {
  
  if(contador%2 === 0 ) {
  
    console.log(contador);
  
  }
  
}
 
```

- Usando *while*
```javascript
   
var contador = 0;

while( contador <=100) {


  if(contador%2 === 0 ) {
  
    console.log(contador);
  
  }

  contador++;  
  
}
   
```

- Usando *Do...While*
```javascript
 
var contador = 0;

do {

  if(contador%2 === 0 ) {
  
    console.log(contador);
  
  }
  
  contador++;

} while (contador<=100)
 
```

**5 -** Diseña un algoritmo que imprima los números impares entre un número dado por el usuario y los siguientes 50 números.

- Usando *for*
```javascript
   
function imprimirImpares (numero) {
  
  for( var totalImpares = 0; totalImpares <= 50; numero++ ) {
  
    if ( numero%2 !== 0 ) {
      
      console.info(numero);
      totalImpares++;
      
    }
    
  }
  
}
   
```

- Usando *while*
```javascript
    // Tu solución
```

- Usando *Do...While*
```javascript
    // Tu solución
```

**6 -** Diseña un algoritmo que imprima la suma de los 50 primeros numeros pares y el total de números impares partiendo de un número dado por el usuario

- Usando *for*
```javascript
    
function totalParesImpares(numero) {

  var totalImpares = 0;
  var totalPares = 0;
  
  // Variable contadora de los números pares
  var numeroPar = 0;
  
  for (numero; numeroPar<=50 ; numero++) {
    
    if ( numero % 2 === 0) {
    
      // Número par
      console.info(numero);
      totalPares = totalPares + numero;
      numeroPar++;
    
    }
    
    else {
    	// Número impar
      
     	console.info(numero);
      totalImpares = totalImpares + numero;
    
    }
 
  }
 
  console.info("La suma total de números pares es: " + totalPares + " y de los impares: " + totalImpares );

}
    
```

- Usando *while*
```javascript
    // Tu solución
```

- Usando *Do...While*
```javascript
    // Tu solución
```

**7 -** Diseña un algoritmo introducido un numero y pasarlo a número romanos.
- Esperamos que el número sea menor de 50

![numeros_romanos](https://eloviparo.files.wordpress.com/2009/09/numeros-romans.jpg?w=466&h=172)

```javascript

function convertirRomanos(numero) {
 	var letraUnidad, letraDecena = "";
  var unidades;
  var decenas;
  
  // Comprobamos que el número introducido sea correcto
  if ( numero>=1 && numero<=50 ) {
  
    
    // Dividimos el número en unidades y decenas
    
    unidades = parseInt(numero % 10);
    decenas = parseInt(numero / 10);
    	
    // Escribimos unidades y decenas
		console.log( "Decenas: " + decenas + " - Unidades: " + unidades);
    
    switch( unidades ) {
    
      case 1:
        letraUnidad = "I";
         break;
        
      case 2:
        letraUnidad = "II";
         break;
        
      case 3:
        letraUnidad = "III";
         break;
        
      case 4:
        letraUnidad = "IV";
         break;
        
      case 5:
        letraUnidad = "V";
         break;
        
      case 6:
        letraUnidad = "VI";
         break;
        
      case 7:
        letraUnidad = "VII";
         break;
        
      case 8:
        letraUnidad = "VIII";
         break;
        
      case 9:
        letraUnidad = "IX";
         break;
        
      case 10:
        letraUnidad = "X";
        break;
        
    
    }
    
      
     switch( decenas*10 ) {
    
      case 10:
        letraDecena = "X";
         break;
        
      case 20:
        letraDecena = "XX";
         break;
        
      case 30:
        letraDecena = "XXX";
         break;
        
      case 40:
        letraDecena = "XL";
         break;
        
      case 50:
        letraDecena = "L";
         break;
           
    }
    
    console.info("Conversión del número " + numero + " a número romano: " + letraDecena +  letraUnidad);

  }
  
  else {
  	console.warn("El número introducido no es correcto");
  
  }
  
  
}


```


- Usando *for*
```javascript
    // Tu solución
```

- Usando *while*
```javascript
    // Tu solución
```

- Usando *Do...While*
```javascript
    // Tu solución
```