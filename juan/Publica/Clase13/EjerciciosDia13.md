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

```





Ejercicio de Buenos dias Madrid
Ejercicios QUnit
