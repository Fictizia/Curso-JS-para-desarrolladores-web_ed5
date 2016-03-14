### Ejercicios

1 - Sacar en el html la respuesta de [OMDB](http://omdbapi.com/) para la pelicula Hackers

```javascript

function peticionAjax (nombreFilm) {
        
  var xmlHttp = new XMLHttpRequest();
  var url = 'http://www.omdbapi.com/?t=' + nombreFilm + '&y=&plot=short&r=json';

        
  xmlHttp.onreadystatechange = function() {

    if (xmlHttp.readyState === 4 && xmlHttp.status === 200) {
      
      //console.info(JSON.parse(xmlHttp.responseText));
      
      var infoFilm = JSON.parse(xmlHttp.responseText);
      
      var contenido = '<h1>Película: ' + infoFilm['Title'] + '</h1>';
      contenido += '<img src="' + infoFilm['Poster'] + '">';
      contenido += '<p><b>Año: </b>' + infoFilm['Year'] + '</p>';
      contenido += '<p><b>Duración: </b>' + infoFilm['Runtime'] + '</p>';
      contenido += '<p><b>Directores: </b>' + infoFilm['Runtime'] + '</p>';
      contenido += '<p><b>Actores: </b>' + infoFilm['Runtime'] + '</p>';
      contenido += '<p><b>Sinopsis: </b>' + infoFilm['Plot'] + '</p>';
      
      document.body.innerHTML = contenido;
      
      
    
    } else if (xmlHttp.readyState === 4 && xmlHttp.status === 404) {
      
      console.error("ERROR! 404");
      console.info(JSON.parse(xmlHttp.responseText));
    
    }
  };
  
  xmlHttp.open("GET", url, true);
  
  xmlHttp.send();
  
}


peticionAjax ('Hackers');
 

```

2 - Sacar en el html el tiempo meteorológico de Madrid, Barcelona y Valencia. 
Nota: http://openweathermap.org te será de gran ayuda, busca la solución al error 401


```javascript

var contenido = '';

function elTiempo (ciudad) {
        
  var xmlHttp = new XMLHttpRequest();
  
   
  var yourApiKey = 'c9db43f368606978d0a1347aa2632cb2';
  var url = 'http://api.openweathermap.org/data/2.5/weather?q=' + ciudad + '&APPID=' + yourApiKey;
 	var infoTiempo;

        
  xmlHttp.onreadystatechange = function() {

    if (xmlHttp.readyState === 4 && xmlHttp.status === 200) {
      
      //console.info(JSON.parse(xmlHttp.responseText));
      
      infoTiempo = JSON.parse(xmlHttp.responseText);
      
      
      contenido += '<p><b>Ciudad: </b>' + infoTiempo.name+ '</p>';
      contenido += '<p>' + infoTiempo.weather[0].description+ '</p>';
      contenido += '<p><b>Temperatura: </b>' + conversionCelsius( infoTiempo.main.temp ) + 'ºC</p>';
       contenido += '<p><b>T.Máxima: </b>' + conversionCelsius( infoTiempo.main.temp_max ) + 'ºC</p>';
       contenido += '<p><b>T.Mínima: </b>' + conversionCelsius( infoTiempo.main.temp_min ) + 'ºC</p>';
      contenido += '<hr>';
        
      document.body.innerHTML = contenido;
      
    } 
    
    else if (xmlHttp.readyState === 4 && xmlHttp.status === 404) {
      
      infoTiempo = JSON.parse(xmlHttp.responseText);
      console.error("ERROR! 404");
      console.info(infoTiempo);
    
    }
    
  };
  
  xmlHttp.open("GET", url, true);
  xmlHttp.send();
  
}


function conversionCelsius (gradosKelvin) {
  
  return parseInt(gradosKelvin) - 273;
}


// Llamada 

elTiempo ('Madrid');
elTiempo ('Barcelona');
elTiempo ('Valencia');

```

