# Clase 8 Ejercicios
## Fechas

2 - ¿Que fecha será dentro de 30 días?
```javascript

var fecha = new Date();
console.log("Fecha de hoy : " + fecha.toLocaleString() );

fecha.setDate(feha.getDate() + 30);
console.log ("Fecha dentro de 30 dias: " + fecha.toLocaleString() );
  
```

3 - ¿Cuantas horas han pasado desde que emepezó este curso? y... ¿en días?
```javascript

function calculoInicioCurso (year, month, day, hour, minute, second) {

  var fechaInicio = new Date(year, month -1 , day, hour, minute, second);
  console.log("Fecha de inicio del curso: " + fechaInicio);
  
  var fechaActual = new Date();
  console.log("Fecha actual: " + fechaActual);
  
  // Tiempo transcurrido desde la fecha de inicio en horas
  var tiempoTotalms = fechaActual.getTime() - fechaInicio.getTime();
  console.log("Tiempo transcurrido en milisegundos desde el inico del curso: " + tiempoTotalms);
  
  
  
  /*
    CONVERSIÓN ms > segundos > minutos > horas
  	1s = 1000ms
    60s = 1 minuto
    60 minutos = 1 hora
    24 horas = 1 día
    
    resultado en horas = X ms * (1s/1000ms) * (1min/60s) * (1h/60min)
    resultado en días = X ms * (1s/1000ms) * (1min/60s) * (1h/60min) * (1dia/24h)
    
  */
  var tiempoTotalHoras = Math.floor ( tiempoTotalms * (1/1000) * (1/60) * (1/60) );
  console.log("Tiempo transcurrido en horas desde el inico del curso: " + tiempoTotalHoras);
  
  var tiempoTotalDias = Math.floor ( tiempoTotalms * (1/1000) * (1/60) * (1/60) * (1/24) );
  console.log("Tiempo transcurrido en días desde el inico del curso: " + tiempoTotalDias);
  

}

// Inicio del curso: 27 de enero de 2016 a las 19:00h
calculoInicioCurso(2016, 1, 27, 19, 0, 0);


```

4 - ¿Cuantos milisengundos quedan para terminar el curso? y... ¿en horas o días?
```javascript

function calculoFinCurso (year, month, day, hour, minute, second) {

  var fechaFin = new Date(year, month -1 , day, hour, minute, second);
  console.log("Fecha de fin de curso: " + fechaFin);
  
  var fechaActual = new Date();
  console.log("Fecha actual: " + fechaActual);
  
  // Tiempo transcurrido desde la fecha de inicio en horas
  var tiempoTotalms = fechaFin.getTime() - fechaActual.getTime();
  console.log("Tiempo transcurrido en milisegundos para finalizar curso: " + tiempoTotalms);
  
  
  
  /*
    CONVERSIÓN ms > segundos > minutos > horas
  	1s = 1000ms
    60s = 1 minuto
    60 minutos = 1 hora
    24 horas = 1 día
    
    resultado en horas = X ms * (1s/1000ms) * (1min/60s) * (1h/60min)
    resultado en días = X ms * (1s/1000ms) * (1min/60s) * (1h/60min) * (1dia/24h)
    
  */
  var tiempoTotalHoras = Math.floor ( tiempoTotalms * (1/1000) * (1/60) * (1/60) );
  console.log("Tiempo transcurrido en horas para finalizar curso: " + tiempoTotalHoras);
  
  var tiempoTotalDias = Math.floor ( tiempoTotalms * (1/1000) * (1/60) * (1/60) * (1/24) );
  console.log("Tiempo transcurrido en días para finalizar curso: " + tiempoTotalDias);
  

}

// Fin del curso: 16 de marzo de 2016 a las 22:00h
calculoFinCurso(2016, 3, 16, 22, 0, 0);


```

5 - ¿Que fecha será dentro de un año y 10 horas más?
```javascript

var fecha = new Date();

console.log("La fecha de hoy: " + fecha.toLocaleString() );

// Fecha dentro de 10 horas más
fecha.setHours ( fecha.getHours() + 10 );

// Fecha dentro de 1 año más
fecha.setFullYear ( fecha.getFullYear() + 1 );

console.log ("La fecha actual dentro de 1 año y 10 horas más: " + fecha.toLocaleString() );

```
6 - Imprimer por consola la fecha completa (formato texto) en koreano, japones.
```javascript
function fechaLocal() {

	var fecha = new Date();
  
  // Formateamos la fecha en coreano
  var opciones = {
  	weekday: 'long',
    year: 'numeric', 
    month: 'long', 
    day: 'numeric'
  }
  

  console.log("Fecha actual: " + fecha.toLocaleString( "es-ES", opciones) );
 
  console.log("Fecha actual en Coreano: " + fecha.toLocaleString( "ko-KR", opciones) );

  console.log("Fecha actual en Japonés: " + fecha.toLocaleString( "ja-JP-u-ca-japanese", opciones) );
}

fechaLocal();

```

## String, Arrays

1 - Diseña un algoritmo que cuente las veces que aparece una determinada letra en una frase.

```javascript

function contarLetraEnFrase ( letra, frase) {

  var fraseSeparada = frase.split("");
  var contador = 0;
  
  
  for ( var i = 0; i<=fraseSeparada.length; i++ ) {
  
    if ( fraseSeparada[i] === letra) {
    
      contador++;
    
    };
  
  };
  
  console.log("La letra \"" + letra + "\" se repite en la frase \"" + frase + "\", " + contador + " veces.");
  
}


contarLetraEnFrase( "i", "Fictizia mola mucho !!!");

```