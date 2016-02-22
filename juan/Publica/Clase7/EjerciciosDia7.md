# Clase 7 Ejercicios
## Bucles

**Ejercicios Números Aleatorios**

1 - Diseña un algoritmo que simula el lanzamiento de una moneda al aire e imprimir si ha salido cara o cruz.

```javascript
    
function lanzarMoneda() {

  
  / *
  	Genera numero aleatorio comprendido entre el 0-2 incluyendo el 0 y excluyendo
    el 2 y luego obtiene la parte entera de dicho número
  
  */
  var moneda = Math.floor( Math.random() * 2);
  //var moneda = Math.floor( Math.random() * (2-0)) + 0;
	
  console.log(moneda);
  moneda===1? console.info("Cara") : console.info("Cruz");
    

}
    
```

2 - Diseña un algoritmo que  simula cien tiradas de dos dados y contar las veces que entre los dos suman 10.

```javascript

function lanzarDados() {


  var dado1 = Math.floor( Math.random() * (7-1)) + 1;
	var dado2 = Math.floor( Math.random() * (7-1)) + 1;
  var sumarTirada;
  var vecesSuma10 = 0;
  
 // simulamos 100 tiradas de dados
  
  for ( var i= 1; i<=100 ; i++ ) {
    
    dado1 = Math.floor( Math.random() * (7-1)) + 1;
		dado2 = Math.floor( Math.random() * (7-1)) + 1;
    sumarTirada = dado1 + dado2;

    if ( sumarTirada === 10 ) {
    
      vecesSuma10 ++;
    
    }
    
  }
  
  console.info ("De 100 lanzamientos de 2 dados han sumado entre los dos 10 un total de " + vecesSuma10);

}

```


**Ejercicios Fechas**

1 - Diseña un algoritmo que confirme si una fecha es valida y además devuelva la fecha en dos formatos diferentes.
- Características:
	- El usuario introduce tres números (día, mes, año) usando una función.
	- Validar la fecha. En caso de error incluir un mensaje informativo.
	- Después de validar, devolvemos la fecha en formato DD/MM/AAAA
	- Convertimos el número del mes, en el nombre del mes real y devolvemos la fecha en el siguiente formato ( DD de MES de AAAA)

```javascript

function validarFecha(dia, mes, anyo) {

  // Validamos que la fecha sea correcta
  
  if( (dia>0 && dia<=31) && (mes>0 && mes <=12) && anyo>=0  ) {
  
    /*
    	Interpretación fecha en JS : 
    		dia 1-31
        mes 0-11 => Formatear el mes restando 1
    		año 4 dígitos
    */
    
     var miFecha = new Date(anyo, mes-1, dia);
    console.log(miFecha);
    
    // Formatear fecha DD/MM/AAAA
    console.log( "Formato de fecha DD/MM/YYYY: " + miFecha.getDate() + "/" + (miFecha.getMonth()+1) + "/" + miFecha.getFullYear() );
    
     
    // Formatear: DD de MES de AAAA
    var opciones = { 
     // weekday: 'long',
      year: 'numeric', 
      month: 'long', 
      day: 'numeric'};
    
    console.log("La fecha: " + miFecha.toLocaleString("es-ES", opciones));
    
  }
 
  else {
   
    console.warn("La fecha introducida no es válida !!!");
  
  }

}

```