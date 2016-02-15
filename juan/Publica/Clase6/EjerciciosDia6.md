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

**6 -** Diseña un algoritmo que imprima la suma de los 50 primeros numeros pares y el total de números impares partiendo de un número dado por el usuario

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

**7 -** Diseña un algoritmo introducido un numero y pasarlo a número romanos.
- Esperamos que el número sea menor de 50

![numeros_romanos](https://eloviparo.files.wordpress.com/2009/09/numeros-romans.jpg?w=466&h=172)

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