# Clase 11

### [DUDA: POO, prototype y this](https://github.com/UlisesGascon/curso-js-web-developers-012016/issues/4)

**THIS**
- Dominando los Contextos de *this*: 
    - Window:
    ```javascript
        console.log( this === window );
 
        function prueba(){
          console.log( this === window);
        }
         
        prueba();
    ```
    - Otro Contexto:
    ```javascript
        var usuario = {
          nombre : 'Yo',
          apellido : 'Mismo',
          nombreCompleto : this.nombre +" "+ this.apellido,
          metodoNombre: function(){
            return this.nombre + " " + this.apellido
          },
          valorThis: function (){
            console.log(this);
          }
        }
        // ERROR - Undefined  -> this=window
        console.log( usuario.nombreCompleto);
        
        // FUNCIONA - this=usuario
        console.log(usuario.metodoNombre());
        
        // FUNCIONA - this=usuario
        usuario.valorThis();
    ```

**POO**

- Programación basada en prototipos

>La programación basada en prototipos es un estilo de programación orientada a objetos en la que las clases no están presentes y la reutilización de comportamiento (conocido como herencia en lenguajes basados en clases) se lleva a cabo a través de un proceso de decoración de objetos existentes que sirven de prototipos. Este modelo también se conoce como programación sin clases, orientada a prototipos o basada en ejemplos.
>[Mozilla developer network](https://developer.mozilla.org/es/docs/Web/JavaScript/Introducci%C3%B3n_a_JavaScript_orientado_a_objetos)

- Constructor de Objetos:
```javascript
	var ahora = new Date();
	
	var coche = function (parametros) {
	    /* Codigo*/
	};
```

- Constructor Simple:
```javascript
    var coche = function (marca, modelo, antiguedad, color, tipo) {
        this.marca = marca;
        this.modelo = modelo;
        this.antiguedad = antiguedad;
        this.color = color;
        this.tipo = tipo;
        this.detalles = function(){
          console.log("Tu coche es un "+this.marca+" "+this.modelo+" con "+this.antiguedad+" años, clase "+this.tipo+" y color "+this.color);
        }
    };

    var miCoche = new coche ("Seat", "Panda", 20, "azul", "turismo");
    miCoche.detalles();
```

- Constructor Complejo (datos privados y no privados):
```javascript
    var cocheEmpresa = function (marca, modelo, antiguedad, color, tipo) {
        // públicas
        this.marca = marca;
        this.modelo = modelo;
        this.antiguedad = antiguedad;
        this.color = color;
        this.tipo = tipo;

        // privadas
        var ITVPasada = true;
        var ITVfrecuencia = "Cada año";
        var seguroEnRegla = true;
        var companySeguros = "SegurExpress";
        var tipoSeguro = "a terceros";

        // Público
        this.dameDetalles = function () {
            console.log("Tu coche es un "+marca+" "+modelo+" con "+antiguedad+" años, clase "+tipo+" y color "+color);
        }

        // Privadas
        function datosPrivados() {
            if (ITVPasada && seguroEnRegla)
                console.info("INFO: Todo en Regla, tienes que pasar la ITV "+ITVfrecuencia+". Tienes un seguro "+tipoSeguro+" con "+companySeguros);
            else{
                console.error("ALERTA! El coche no puede usarse. El seguro o la ITV no esta en regla.");
            }
        }

        datosPrivados();
        this.dameDetalles();
    };

    var miCoche = new cocheEmpresa ("Audi", "S8", 2, "negro", "Berlina");
    var miCoche2 = new cocheEmpresa ("Audi", "S4", 2, "Rojo", "Compacto");
```

- Herencia:
```javascript
	var coche = function (marca, modelo, antiguedad, color, tipo) {
	    this.marca = marca;
	    this.modelo = modelo;
	    this.antiguedad = antiguedad;
	    this.color = color;
	    this.tipo = tipo;
	    this.detalles = dameDetalles;
	};

	var furgon = function (taraMinima, cargaUtil, volumenCarga) {
	    this.taraMinima = taraMinima;
	    this.cargaUtil = cargaUtil;
	    this.volumenCarga = volumenCarga;
	    this.detallesTecnicos = detallesTecnicos;
	};


	function dameDetalles(){
	  console.log("Tu coche es un "+this.marca+" "+this.modelo+" con "+this.antiguedad+" años, clase "+this.tipo+" y color "+this.color);
	}

	function detallesTecnicos(){
	  console.warn("Tu coche tiene una Tara mínima de "+this.taraMinima+". Carga útil de "+this.cargaUtil+" y un volumen de carga de "+this.volumenCarga+"m3");
	}

	var miPickup = new coche ("Land Rover", "Santana Aníbal", 35, "Marrón tierra", "4x4");
	miPickup.prototype = new furgon (1200, 768, 4.5);


	miPickup.detalles();
	miPickup.prototype.detallesTecnicos();
```

- Herencia simple (prototype):
```javascript
    var perro  = function () {
        this.patas = 4;
        this.ojos = 2;
    };

    var pastorAleman = function () {
        this.colorLengua = "negra";
        this.colorOjos = "marrón";
        this.capacidadTrabajo = true;
        this.especialidad = "Pastoreo";
    };

    pastorAleman.prototype = new perro();

    var miPerro = new pastorAleman();
    console.log("Número patas: "+miPerro.patas+"\n Número ojos: "+miPerro.ojos+"\n Color Lengua: "+miPerro.colorLengua+"\n Color ojos: "+miPerro.colorOjos+"\n Capacidad de trabajo: "+miPerro.capacidadTrabajo+"\n Especialidad: "+miPerro.especialidad);
```

**POO (sin constructores)**

- Object.create(coche):

```javascript
    var coche = {
        marca: "Seat",
        modelo: "Panda",
        antiguedad: 20,
        color: "azul",
        tipo: "turismo"
    };
    
    var clonCoche = Object.create(coche);
    
    console.log(clonCoche.marca+" "+clonCoche.modelo);
    
    var copiaCoche = coche;
    
    console.info("¿Coche es el prototipo de ClonCoche?", coche.isPrototypeOf(clonCoche));
    console.warn("¿Coche es el prototipo de copiaCoche?", coche.isPrototypeOf(copiaCoche));

```

**Prototype en Objetos Nativos**
- Puedo crear nuevos métodos:
```javascript
	Array.prototype.coincidencias = function(palabra) {
        var coincidencias = 0;
        for (var i=0; i<this.length; i++) {
            if (this[i] == palabra) {
                coincidencias++;
            }
        }
        console.warn("Se encontraron "+coincidencias+" coincidencia(s) de la palabra");
    };


    var amigos = ["Charlie", "Marco", "Luis", "Jose", "Miguel", "Jose", "Luis", "Oscar"];
    amigos.coincidencias("Jose");
```

- Incluso puedo modificar métodos existentes:
```javascript
Array.prototype.push = function () {
console.info("Array.push() ya no funciona");
};
```


### BOM (Browser Object Model)

![DOM, BOM y JS](http://javascript.info/files/tutorial/browser/JSTop.png)

**window.history**
- propiedades:
```javascript
	history.length
```
- Métodos:
```javascript
	// Ir atras
	history.go(-1);
	history.back();
	
	// Ir adelante
	history.go(1);
	history.forward();
```

**window.navigator**
- Propiedades:
```javascript
	function conversorTiempo(segundos){
		var fecha = new Date(segundos * 1000);
		var hh = fecha.getUTCHours();
		var mm = fecha.getUTCMinutes();
		var ss = fecha.getSeconds();

		if (hh < 10) {hh = "0"+hh;}
		if (mm < 10) {mm = "0"+mm;}
		if (ss < 10) {ss = "0"+ss;}

		return hh+":"+mm+":"+ss;
	}

	function informacionSistema(){
		console.log("appCodeName:", window.navigator.appCodeName);
		console.log("appName:", window.navigator.appName);
		console.log("appVersion:", window.navigator.appVersion);
		console.log("platform:", window.navigator.platform);
		console.log("product:", window.navigator.product);
		console.log("userAgent:", window.navigator.userAgent);
		console.log("javaEnabled:", window.navigator.javaEnabled());
		console.log("language (used):", window.navigator.language);
		console.log("language (support):", window.navigator.languages);
		console.log("conectado a internet?", window.navigator.onLine);
		console.log("mimeTypes:",window.navigator.mimeTypes);
		console.log("Plugins:", navigator.plugins);

		navigator.getBattery().then(function(bateria){
			console.log("Batería cargando?", bateria.charging)
			
			if(bateria.charging){
				console.log("Tiempo de carga:", bateria.chargingTime)
			}
			console.log("Batería %:", bateria.level*100)
			console.log("Tiempo restante:", conversorTiempo(bateria.dischargingTime))

		});

	}
```

**window.screen**
- Propiedades:
```javascript
	function informacionPantalla(){
		console.log("availTop:", window.screen.availTop);
		console.log("availLeft:", window.screen.availLeft);
		console.log("availHeight:", window.screen.availHeight);
		console.log("availWidth:", window.screen.availWidth);
		console.log("colorDepth:", window.screen.colorDepth);
		console.log("height:", window.screen.height);
		console.log("left:", window.screen.left);
		console.log("orientation:", window.screen.orientation);
		console.log("pixelDepth:", window.screen.pixelDepth);
		console.log("top:", window.screen.top);
		console.log("width:", window.screen.width);
	}
```



**Window.location y Document.location**

- Propiedades:
```javascript
	function informacionEnlace(url){
	
		var enlace = document.createElement('a');
		enlace.href = url || 'https://fictizia.com:3000/formacion/curso_javascript?q=JS#contenido-curso';
		
		console.log("href:" ,enlace.href);
		console.log("protocol:", enlace.protocol);
		console.log("host:", enlace.host);
		console.log("hostname:", enlace.hostname);
		console.log("port:", enlace.port);
		console.log("pathname:", enlace.pathname);
		console.log("search:", enlace.search);
		console.log("hash:", enlace.hash);
		console.log("origin:", enlace.origin);
	}
```

- Métodos:
	- .assign() *Carga una página nueva*
	```javascript
		document.location.assign('http://fictizia.com/formacion/curso_javascript');
	```
	- .reload() *Recarga*
	```javascript
		document.location.reload(); // Recarga
		document.location.reload(true); // Recarga sin usar el cache
		document.location.reload(forcedReload); // Recarga SIEMPRE sin usar el cache
	```
	- .replace() *Carga una página nueva, sustituyendo la actual en el historial*
	```javascript
		document.location.replace('http://fictizia.com/formacion/curso_javascript');
	```
	- .toString() *Devuelve el href como cadena*
	```javascript
		var enlace = document.createElement('a');
		enlace.href = 'http://fictizia.com/formacion/curso_javascrip';
		
		console.log("toString:" ,enlace.toString());
	```


### DOM

- **[DOM - Document Object Model](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model)**
- **[Element](https://developer.mozilla.org/en-US/docs/Web/API/Element)**
- **[Node](https://developer.mozilla.org/en-US/docs/Web/API/Node)**
- **[NodeList](https://developer.mozilla.org/en-US/docs/Web/API/NodeList)**


IMPORTANTE:  Los retornos de *Node.childNodes* y *document.querySelectorAll* - NO son arrays. 

```javascript

var listaDivs = document.querySelectorAll('div');

// Iteración
for (var i = 0; i < listaDivs.length; ++i) {
  var elemento = listaDivs[i];
  console.log("Elemento: ", elemento);
}

// Conversión
var listaDivsArray = Array.prototype.slice.call(listaDivs);
```

### Estilos con Javascript
```javascript
// getter
window.getComputedStyle(document.getElementById("id"));
window.getComputedStyle(document.body).getPropertyValue('display');
// setter
document.body.style.display="none";
document.getElementById("id").style.display="none";
```


### Selectors

- [Soporte](http://caniuse.com/#search=querySelector)

- Convencional:
    - getElementById():
    ```javascript
        // <tag id = "x" >
        document.getElementById("id");
    ```
    
    - getElementsByName():
    ```javascript
        // <tag name = "x" >
        document.getElementsByName("fname");
    ```
    
    - getElementsByTagName():
    ```javascript
        // <tag >
        document.getElementsByTagName("input");
    ```

- Selectores CSS3:

    - URL que empieza con "javascript:"
    ```javascript
        a[href^="javascript:"] {color:blue;}
    ```
    
    - URL que contiene "google.es"
    ```javascript
        a[href*="google.es"] {color:orange;}
    ```
    
    - URL que termina con ".pdf"
    ```javascript
        a[href$=".pdf"] {color:red;}
    ```


- Comprobando disponibilidad del API:
```javascript
// op.1 - Positivo

    if( document.querySelector && document.querySelectorAll ){
        console.info("querySelector() y querySelectorAll() estan soportados!!")
    } else {
        console.warn("querySelector() y querySelectorAll() no estan soportados!!")
    }
// op.2 - Negativo

    if( typeof document.querySelector !== "function" && typeof document.querySelectorAll !== "function" ){
        console.warn("querySelector() y querySelectorAll() no estan soportados!!")
    } else {
        console.info("querySelector() y querySelectorAll() estan soportados!!")
    }

```

- querySelector():
Devuelve el primer elemento que coincida con el selector 

```html
    <div id="miDiv">
        <span id="miId5" class="miClase" title="cinco"></span>
        <span id="miId4" class="miClase" title="cuatro"></span>
        <span id="miId3" class="miClase" title="tres"></span>
        <span id="miId2" class="miClase" title="dos"></span>
        <span id="miId1" class="miClase" title="uno"></span>
    </div> 
```

```javascript
    document.getElementById('miId1').title // uno
    document.querySelector('#miDiv .miClase').title // cinco
    document.querySelector('#miDiv #miId1.miClase').title // uno
    document.querySelector('#miDiv .inventado').title // ERROR -> undefined
    document.querySelector('#miDiv .miClase[title^=u]').title // uno
```

- querySelectorAll():
Devuelve todos los elementos que coincida con el selector en un array
```javascript
    document.querySelectorAll('#miDiv .miClase') // [<span id="miId5" ... ]
    document.querySelectorAll('p') // todos los parrafos
    document.querySelectorAll('div, img') // todos los divs e imágenes
    document.querySelectorAll('a > img') // todos las imágenes contenidas en enlaces
```

### Trabajar sin JQuery

- **[You Might Not Need Jquery](http://youmightnotneedjquery.com/)**
- **[You Might Not Need Jquery(en GitHub)](https://github.com/HubSpot/youmightnotneedjquery)**

**Ejercicios:**


**1 -**  Diseña un algoritmo que sustituya todas las imágenes de las entradas de [Genbeta](http://www.genbeta.com/) por [imágenes dummy de gatitos](https://placekitten.com/).
```javascript
	// Tu solución
```

**2 -** Diseña un algoritmo que agrupe todos los titulares, sus autores y categorias dentro de [Genbeta:dev](http://www.genbetadev.com/) y luego vacíe el html para cargar una lista hecha por nosotros con la información previamente recolectada.
```javascript
	// Tu solución
```