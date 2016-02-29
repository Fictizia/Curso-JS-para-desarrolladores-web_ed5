# Clase 9 Ejercicios

## Arrays

2 - Junta estos tres Arrays *["Oscar", ...], [9897667, ...], [false, ...]* de tal forma que construyan un único Array anidado *[["Oscar", 9897667, false], [etc...]]* 
```javascript

	
var arreglo1 = ["Oscar", "Pedro", "Marco", "Juana"],
		arreglo2 = [9897667, 81721623, 91823871, 71236123],
		arreglo3 = [false, true, true, false];
		
//Juntamos los 3 arrays en uno solo   
var arregloTotal = [];


for ( var i=0; i< arreglo1.length; i++ ) {
  
  arregloTotal.push( arreglo1[i], arreglo2[i], arreglo3[i] );

}

console.log ( arregloTotal );

```

3 - Crea un Array con 100 numeros enteros al azar. Después crea un array para almacenar los números pares y otro array para los impares.

- Opcional: Ordena los números pares e impares en sus respectivos arrays

```javascript

var arregloNumeros = [];
var arregloPares = [];
var arregloImpares =[];
var numeroAzar;


for ( var i=0; i<100; i++) {
  
  // Generamos números enteros del 1-9
  numeroAzar = Math.floor( Math.random() * (10-1) ) + 1;
 
  arregloNumeros.push(numeroAzar);
 
  if ( numeroAzar%2 ===0 ) {
  	// Número Par
    arregloPares.push( numeroAzar );
  }
  else {
  	// Número Impar
    arregloImpares.push( numeroAzar );
  }
  
} 

// Ordenar los números de los arrays Pares e Impares
arregloPares = arregloPares.sort();
arregloImpares = arregloImpares.sort();

```

4 - Vamos a gestionar la lista de asistentes de un evento. 

- Características:
	- Cada asistente recibirá el identificador de su posición en el Array.
	- El identificador no puede cambiar una vez reservado el asiento.
	- Los asistentes pueden darse de baja, y el asiento que ocupaban queda libre.
	- Los nuevos asistentes seran asigandos primero a asientos desocupados. 

- Opcional:
	- Verifica antes de asignar un asistente que no se registro previamente. 

```javascript

// Lista de asistentes al evento
var lista = [];


function addAsistenteEvento ( nombre ) {
  
  var asientoDesocupado = false;
  
   	// Recorremos la lista de asistentes al evento buscando asientos desocupados
    for ( var i= 0; i<lista.length; i++ ) {
     
      if ( lista[i] === undefined ) {
        //Existe un asiento desocupado.Asignamos dicho asiento al asistente
        asientoDesocupado = true;
        lista[i] = nombre;
        console.info('Añadido a la lista del evento: \"' + nombre + '\" con identificador: \"' + lista.indexOf(nombre) + '\"');
        break;
      }
   
    }
 
  if ( !asientoDesocupado ) {
     // No hay asientos desocupados. Añadimos nuevo asiento al asistente
  	lista.push(nombre);
   console.info('Añadido a la lista del evento: \"' + nombre + '\" con identificador: \"' + lista.indexOf(nombre) + '\"');
  }
      
}


function bajaAsistenteEvento ( nombre ) {
  
  // Buscamos el identificador aisgnado al nombre 
  var identificador = lista.indexOf(nombre);
  console.log ('Identificador; ' + identificador);
  
  // Comprobar: La lista no este vacia y el elemento a borrar exista en la lista
  
  if ( lista.length !== 0 && lista[identificador] === nombre ) {
     
    console.info('Eliminamos a \"' + nombre + '\" de la lista de asistentes');
    delete lista[ identificador ];
 
  }
  
  else {
    
     // La lista esta vacía o no existe el asistente 
  	console.info('La lista de asistentes al evento está vacia o no existe el nombre del asistente a dar de baja.');
  
  }

  
}

// Añadimos asistentes al evento
addAsistenteEvento ('Juan');
addAsistenteEvento ('Pol');
addAsistenteEvento ('Luís');
addAsistenteEvento ('Maria');

// lista de asistentes al evento
console.info('Asistentes al evento: ' + lista);

// Damos de baja un aistente
bajaAsistenteEvento ('Pol');
console.info('Asistentes al evento: ' + lista);

// Asignamos un nuevo asistente a la lista
addAsistenteEvento ('Pedro');

// Nueva lista de asistentes al evento
console.info('Asistentes al evento: ' + lista);


```


## Objetos

**Ejercicios**

![img](http://s7d2.scene7.com/is/image/samsclub/0040617419099_A?wid=1500&hei=1500&fmt=jpg&qlt=80)

Práctica 1 - Diseña un script para gestionar por consola una máquina expendedora

Características:
- Solo los usuarios registrados pueden usar la máquina
- El sistema funciona sin dinero real, en su lugar se usa un sistema de puntos
- Los usuarios disponen de unos puntos para gastar en la máquina que el departamento de personal asigna.
- La maquina no concederá creditos, solo trabaja en base a los puntos disponibles.
- Para agilizar la reposición de lo consumido... la maquina debe controlar en stock

Paso 1 - Creamos los primeros objetos básicos:
- Maquina Expendedora (Objeto)
- Productos (Array)
- Clientes (Array)

```javascript

var oMaquinaExpendedora = { }
var productos = ['patatas', 'agua', 'galletas', 'chocolatinas', 'caramelos' ];
var clientes = [];


```

Paso 2 - Creamos los primeros perfiles en el Array de clientes:
- Propiedades:
    - Nombre
    - Usuario
    - Contraseña
    - Tipo usuario
    - Presupuesto

```javascript

// Función constructora del Objeto Cliente
function Cliente( nombre, usuario, password, tipoUsuario, presupuesto ) {

  this.nombre = nombre;
  this.usuario = usuario;
  this.password = password;
  this.tipoUsuario = tipoUsuario;
  this.presupuesto = presupuesto;
}


var oCliente1 = new Cliente('Juan', 'juan', 'p_juan', 'empleado', 10);
var oCliente2 = new Cliente('Maria', 'maria', 'p_maria', 'empleado', 10);
var oCliente3 = new Cliente('Elisa', 'elisa', 'p_elisa', 'empleado', 10);
var oCliente4 = new Cliente('Cesar', 'cesar', 'p_cesar', 'jefe', 10);


clientes.push(oCliente1);
clientes.push(oCliente2);
clientes.push(oCliente3);
clientes.push(oCliente4);

```

Paso 3 - Creamos varios métodos para gestionar a los clientes y sus necesidades

- Metodos:
    - Consultar saldo de un cliente
        - Devolverá el saldo existente o *-1* en caso de error
        - Comprobaremos la contraseña y el usuario
    - Consultar gastos de un cliente
        - Devolverá un array o *false* en caso de error
        - Comprobaremos la contraseña y el usuario
    - Agregar un cliente
    - Eliminar un cliente

- Caracteristicas:
    - Evitaremos que se registren usuarios que ya existan
    - Evitaremos eliminar usuarios que no existan
    - Evitaremos dar de alta usuarios que no esten debidamente cumplimentados
    - Protegeremos las funciones de gestión de usuarios con la contraseña *ficticiaMola*

```javascript
	
// Consultar saldo de cliente
function consultarSaldo ( usuario, password ) {
	
	var saldo;
  
  for ( var i=0; i<clientes.length; i++  ) {
  
    if ( clientes[i].usuario === usuario && clientes[i].password === password ) {
       
      saldo = clientes[i].presupuesto; 
    	break;
      
    }
    else
    {
     // El usuario no existe;
      saldo = -1;
    }
    
    
  }
  
  return saldo
 
}
```

```javascript
// Agregar un cliente
function agregarCliente ( nombre, usuario, password, tipoUsuario, presupuesto, passwordAdmin ) {


  var passwordAcceso = 'fictiziaMola';
  var usuarioExiste = false;


  // Comprobamos que tenga permiso de Administrador para dar de alta un nuevo usuario

  if ( passwordAcceso === passwordAdmin ) {

    // Comprobamos que el usuario a dar de alta no exista previamente en el sistema
    for ( var i=0; i<clientes.length; i++  ) {

      if ( clientes[i].usuario === usuario ) {

        usuarioExiste = true;
        console.warn('Este usuario ya existe en el sistema');
        break;

      }

    }

    if ( !usuarioExiste ) {

      // El usuario no existe en el sistema. Creamos un nuevo usuario con los datos proporcionados
      var oCliente = new Cliente (nombre, usuario, password, tipoUsuario, presupuesto );

      clientes.push(oCliente);
      console.info('Nuevo usuario dado de alta en el sistema');
    }

  }


  else {
    console.warn('Únicamente el adminstrador tiene permiso para añadir nuevos usuarios al sistema.');
  }


}
	
```

```javascript

// Eliminar un cliente
function eliminarCliente ( usuario, passwordAdmin ) {
  
 
  var passwordAcceso = 'fictiziaMola';
  var usuarioExiste = false;
  
  
  // Comprobamos que tenga permiso de Administrador para dar de alta un nuevo usuario
  
  if ( passwordAcceso === passwordAdmin ) {
    
    // Comprobamos que el usuario a dar de alta no exista previamente en el sistema
    for ( var i=0; i<clientes.length; i++  ) {
  
      if ( clientes[i].usuario === usuario ) {
       
         
        // Eliminamos el cliente del sistema y actualizamos la lista de clientes
       
        usuarioExiste = true;
        console.warn('El usuario \"' + clientes[i].usuario + '\" ha sido eliminado del sistema');
        clientes.splice( i, 1);
        break;
        
      }
    
    }
    
    if (!usuarioExiste) {
    
      // El usuario no existe en el sistema. Creamos un nuevo usuario con los datos proporcionados
     	console.warn('El usuario no existe en el sistema');
    }
  
  }
  
 
  
  else {
   console.log(usuarioExiste);
    console.warn('Únicamente el adminstrador tiene permiso para añadir nuevos usuarios al sistema.');
  }
  

}


```


Paso 4 - Creamos varios métodos para gestionar a los productos y sus necesidades
 
- Creamos 5 productos que estarán disponibles a la venta 

- Métodos:
    - Consumir un producto (cliente)
        - Comprobaremos la contraseña y el usuario
        - Devolverá el prodcuto o *-1* en caso de no existir o estar agotado
        - Actualizaremos el stock
        - Actualizaremos el saldo del cliente
    - Agregar un producto a la máquina (administración)
    - Eliminar un prodcutos de la máquina (administración)

- Caracteristicas:
    - Evitaremos agregar prodcutos que ya existan
    - Evitaremos eliminar productos que no existan
    - Evitaremos agregar productos que no esten debidamente cumplimentados
    - Protegeremos las funciones de agregar y eliminar productos con la contraseña *ficticiaMola*

```javascript
	// Tu solución
```

Paso 5 - Ahora podemos agregar los métodos para agregar, retirar y resetear saldo de los usuarios.

- Importante:
	- Los saldos jamas pueden ser negativos.

```javascript
	// Tu solución
```

Paso 6 - Ahora podemos agregar el método para saber la disponibilidad de stock

- Importante:
	- Es necesaria clave (adminsitrador)
	- Debemos saber las existencias
	- Debemos saber que productos estan disponibles y cuales no.
	- Debemos incluir el código y el nombre
	- Cuando se imprima el informe... es necesario incluir la fecha.

```javascript
	// Tu solución
```