## Eventos

- Los eventos permiten aislar completamente mi código del HTML.
- Capture Phase (fase de captura)
- Bubbling Phase (fase de burbujeo)



Hacen lo mismo pero la segunda es para navegadores <=IE8
.addEventListener()
.attachEvent()

Como no sabemos que navegador usará el usuario, creamos una comprobación para validar
si el navegador es antiguo ".attachEvent()" o moderno ".addEventListener()".

## AJAX

Todo lo que se trabaja con APIs se realiza Ajax. Estas NO bloquean el código entre petición y petición y no tenemos la necesidad de 
recargar el navegador, evitando tener que volver a descargartodo el código de la aplicación.

Ajax es una funcionalidad que nos da el navegador (todos lo soportan).

Funcionamiento de la web: Marcamos mi peticion http://... se resuelve en el DNS y la envia al servidor indicado el cual retornará una respuesta.
Nos interesarán los códigos de estado HTTP:
- todos los códigos 100 no interesan
- todos los códigos 200 nos interesan
- los 300 son códigos de redirección
- todos los errores 400 son errores nuestros. El más importante el 404 (petición no encontrada)
- todos los 500 son errores del servidor que no podremos solucionar


La información que se retorna son JSON (los mejores), XML (difíciles de parsear) y los TXT (son los peores).


La información que retorna una API suelen ser archivos JSON. Estos se parsean en javascript y extraemos la información.
La mejor página para poder visualizar los archivos json (su estructura interna): http://jsonviewer.stack.hu/

Tipo de petición que podemos realizar a la API:
- POST: Publicar datos
- GET: Obtener datos
- PUT: Modificar datos
- DELETE: Eliminar datos


Antiguamente existia el JSONP, que es un JSON de javascript (no es un JSON normal). Trae un script en mitad de ejecución

Scraping es robar datos de una API y montarlos en otra API propia


Cuando no esta habilitada la transferencia de datos de un sitio a otro debemos puentear porque daun error de CROSS
La aplicación para puentear cros