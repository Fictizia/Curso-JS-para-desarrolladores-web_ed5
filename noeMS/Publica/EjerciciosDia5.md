Realiza los siguientes ejercicios usando en cada uno los tres tipos de condicionales (If...else, Switch, operador ternario )

**1 -** Diseña un algoritmo que lea dos números y los compare. Como resultado esperamos que nos diga cual es mayor... o si son iguales.

- Usando *if...else*
```javascript
    num1 = prompt("Dame un número");
num2 = prompt("Dame otro número");

if (num1 == num2) {
	console.log("Los números son iguales");
} else if (num1>num2) {
	console.log("El " + num1 + " es mayor que " + num2);
} else {
	console.log("El " + num1 + " es menor que " + num2);
}
```

- Usando *Operador Ternario (?:)*
```javascript
   num1 = prompt("Dame un número");
num2 = prompt("Dame otro número");

(num1 > num2) ? (console.log("El " + num1 + " es mayor que " + num2)) : (num1 < num2) ? (console.log("El " + num1 + " es menor que " + num2)) : console.log("Los números son iguales")
```

- Usando *Switch*
```javascript
    num1 = prompt("Dame un número");
num2 = prompt("Dame otro número");

switch (true) { //porque sino no puedes hacer comparación, parte de true y mira si las comparaciones son true o false. Se usa más para strings que para números
  case num1==num2:
    console.log("Los números son iguales");
    break;
  case num1>num2:
    console.log("El " + num1 + "es mayor que " + num2);
    break;
  case num1<num2:
    console.log("El " + num1 + "es menor que " + num2);
    break;
}
```

**2 -** Diseña un algoritmo que lea tres números distintos y nos diga cual de ellos es el mayor.

- Usando *if...else*
```javascript
   num1 = prompt("Dame un número");
num2 = prompt("Dame otro número");
num3 = prompt("Dame un último número");

if ( num2 > num3 && num2 > num1) {
	console.log (num2 + "es mayor");
} else if ( num3 > num1) {
	console.log(num3 + "es mayor");
} else {
	console.log(num1 + "es mayor");
}
```

- Usando *Operador Ternario (?:)*
```javascript
   num1 = prompt("Dame un número");
num2 = prompt("Dame otro número");
num3 = prompt("Dame un último número");

(num1 > num2 && num1>num3) ? (console.log("El " + num1 + "es mayor")) : (num2 > num3) ? (console.log("El " + num2 + " es mayor")) : console.log(num3 + "es mayor")
```

- Usando *Switch*
```javascript
  num1 = prompt("Dame un número");
num2 = prompt("Dame otro número");
num3 = prompt("Dame un último número");

switch (true) { 
  case (num1>num2 && num1>num3):
    console.log(num1 + "es mayor");
    break;
  case num2>num3:
    console.log(num2 + "es mayor");
    break;
  default:
    console.log(num3 + "es mayor");
    break;
}
```

**3 -** Diseña un algoritmo que siga el siguiente proceso:
- Si el primero es negativo, debe sumar los otros dos
- Sino multiplicará los tres numeros
- Mostrar el resultado final incluyendo una referencia a la operación realizada.

- Usando *if...else*
```javascript
   num1 = prompt("Dame un número");
num2 = prompt("Dame otro número");
num3 = prompt("Dame un último número");

if (num1<0) {
	console.log("Cómo " +  num1 + " es negativo, el producto de " + num2 + " por " + num3 + " es " + (num2*num3))
} else {
	console.log("Cómo " +  num1 + " es positivo, el producto de los tres números es " + (num1*num2*num3))
}
```

- Usando *Operador Ternario (?:)*
```javascript
    // Tu solución
```

- Usando *Switch*
```javascript
    // Tu solución
```

**4 -** Diseña un algoritmo que aplique al precio de un producto un descuento cuando se den las siguientes caracteristicas.
- Se aplica un 25% cuando:
	- Estamos en los meses de invierno
	- Y no es viernes o fin de semana.

- Usando *if...else*
```javascript
mes = prompt("Dime un mes");
dia = prompt("Dime un día");
console.log(mes, dia)

if ( (mes == "enero" || mes == "febrero" || mes == "marzo") && (dia != "viernes" || dia != "sabado" || dia != "domingo") ) {
	console.log("Enhorabuena, tiene usted un 25% de descuento")
} else {
	console.log("Lo sentimos, no le corresponde ningún descuento")
}
```

- Usando *Operador Ternario (?:)*
```javascript
    // Tu solución
```

- Usando *Switch*
```javascript
    // Tu solución
```

**5 -** Diseña un algoritmo que al introducir un numero nos diga si es positivo o negativo.

- Usando *if...else*
```javascript
   num1 = prompt("Dame un número");

if (num1<0) {
	console.log("El número es negativo")
} else {
	console.log("El número es positivo")
}
```

- Usando *Operador Ternario (?:)*
```javascript
    num1 = prompt("Dame un número");

(num1 < 0) ? (console.log("El número es negativo")) : console.log("El número es positivo")
```

- Usando *Switch*
```javascript
    num1 = prompt("Dame un número");

switch (true) { 
  case num1<0:
    console.log("El número es negativo");
    break;
  case num1>0:
    console.log("El número es positivo")
    break;
}
```


**6 -** Diseña un algoritmo que al introducir un número nos diga si es par o impar.

- Usando *if...else*
```javascript
    // Tu solución
```

- Usando *Operador Ternario (?:)*
```javascript
    // Tu solución
```

- Usando *Switch*
```javascript
    // Tu solución
```


**7 -** Diseña un algoritmo que nos confirme si un [año es bisiesto](https://es.wikipedia.org/wiki/A%C3%B1o_bisiesto) o no.
- Caracteristicas de un año bisiesto:
	- Tiene que ser divisible entre 4
	- No tiene que ser divisible entre 100
	- Puede ser divisble entre 100 y entre 400

- Usando *if...else*
```javascript
    // Tu solución
```

- Usando *Operador Ternario (?:)*
```javascript
    // Tu solución
```

- Usando *Switch*
```javascript
    // Tu solución
```