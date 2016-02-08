````
var nombre = prompt("¿Cómo te llamas?");
var respuesta = confirm("¿Quieres saber cómo de rápido es tu ordenador?");
```
```

if (respuesta === true) {
	console.time("calc");
	console.log('%c %s', 'background: #000; color: #FFF; font-size:25px;', nombre);
	console.timeEnd("calc");
} else {
    alert("OH NO QUIERES!!!!!! :( :( :(")
}

```

1 - Diseña un algoritmo que lea dos números y realice los siguientes cálculos:
- Valor de su suma
- Valor de su resta
- Valor de su division
- Valor de su producto

```
var num1 = prompt("Dime un número");
var num2 = prompt("Dime otro número");

console.log("El primer número es", num1);
console.log("El segundo número es", num2);
console.log("Esto no es una suma", num1+num2);
console.log("La resta vale", num1-num2);
console.log("La multiplicación vale", num1*num2);
console.log("La división vale", num1/num2);

```

2 - Diseña un algoritmo para calcular el porcentaje de hombres y mujeres en nuestro curso.
- Trucos:
	- Calcular porcentajes (segmento*100)/total

```

var hombres = prompt("¿Cuantos hombres hay en clase?");
var total = prompt("¿Cual es el total de personas en clase?");

console.log("El % de hombres en clase es", (hombres*100)/total);

```