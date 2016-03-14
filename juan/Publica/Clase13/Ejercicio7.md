![OpenWeatherMap_logo](https://upload.wikimedia.org/wikipedia/commons/1/15/OpenWeatherMap_logo.png)
![Madrid_logo](http://babytribu.com/wp-content/uploads/2012/09/AyuntamientoMadrid.png)

**7 -** Realizaremos una aplicación que nos facilite toda la información necesaria para tomar buenas decisiones por la mañana. Nuestra Aplicación *Buenos Días, Madrid!* necesitará:
- El estado de la contaminación en Madrid
- El estado del tiempo ahora mismo
- La previsión meteorológica de los próximos 4/5 días
- Una imagen aleatoria del trafico de la ciudad usando las cámaras abiertas de la ciudad.

**Recursos:**
- Para localizar los datos de la contaminación en tiempo real en formato .json puedes usar [aireMadrid](http://airemadrid.herokuapp.com/)
	- [API -Media de la red- .json](http://airemadrid.herokuapp.com/api/estacion/99)
	- [Documentacion Oficial](https://github.com/UlisesGascon/Aire-Madrid#api)

- [OpenWeatherMap](http://openweathermap.org) te facilitará toda la información meteorólogica
	- [API Doc](http://openweathermap.org/api)

- [El portal de datos abiertos de Madrid](http://datos.madrid.es/portal/site/egob) te ofrece [los datos y ubicaciones de las cámaras de trafico](http://datos.madrid.es/portal/site/egob/menuitem.c05c1f754a33a9fbe4b2e4b284f1a5a0/?vgnextoid=8803c23866b93410VgnVCM1000000b205a0aRCRD&vgnextchannel=374512b9ace9f310VgnVCM100000171f5a0aRCRD)
**Trucos:**
- Encuentra la lógica en el nombre de las imagenes de las cámaras de tráfico para poder usar un número aleatorio.
- OpenWeatherMap admite parámetros adicionales para devolver los datos en [sistema decimal](http://openweathermap.org/forecast5#data) y en [español](http://openweathermap.org/forecast5#multi).




```javascript


var contenido = '';

function elTiempo () {
        
  var xmlHttp = new XMLHttpRequest();
  var ciudad = 'Madrid';
  var yourApiKey = '&APPID=c9db43f368606978d0a1347aa2632cb2';
  var unidades = '&mode=json&units=metric'
  var idioma = '&lang=sp'
  
  
  var url = 'http://api.openweathermap.org/data/2.5/weather?q=' + ciudad + unidades + idioma + yourApiKey;
  var datos;

        
  xmlHttp.onreadystatechange = function() {

    if (xmlHttp.readyState === 4 && xmlHttp.status === 200) {
      
      
      datos = JSON.parse(xmlHttp.responseText);
      console.info(datos);
      
      contenido += '<h1>Buenos Días, '+ datos.name + '</h1>';
      contenido += '<hr>';
      contenido += '<img src="http://openweathermap.org/img/w/' + datos.weather[0].icon+ '.png">';
      contenido += '<p><b>Descripción: </b>' + datos.weather[0].description+ '</p>';
      contenido += '<p><b>Temperatura: </b>' + datos.main.temp + 'ºC</p>';
      contenido += '<p><b>Min: </b>' + datos.main.temp_min + 'ºC <b>| Max: </b>' + datos.main.temp_max + ' ºC</p>';
      contenido += '<p><b>Humedad: </b>' + datos.main.humidity + ' %</p>';
      contenido += '<p><b>Presión: </b>' + datos.main.pressure + ' psi</p>';
      contenido += '<p><b>Viento: </b>' + datos.wind.speed + ' m/s | <b>Dirección: </b>' + datos.wind.deg +' deg</p>';

        
      document.body.innerHTML = contenido;
      
    } 
    
    else if (xmlHttp.readyState === 4 && xmlHttp.status === 404) {
      
      datos = JSON.parse(xmlHttp.responseText);
      console.error("ERROR! 404");
      console.info(datos);
    
    }
    
  };
  
  xmlHttp.open("GET", url, true);
  xmlHttp.send();
  
}



// El tiempo en Madrid
elTiempo ();

	
```

**Concepto:**

![buenos_dias_madrid.png](../otros/buenos_dias_madrid.png)


