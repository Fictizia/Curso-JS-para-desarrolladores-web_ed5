9 -  Diseña un algoritmo para identificar a los clientes autorizados a entrar a nuestro sistema.
- Características:
	- La palabra clave es "Fictizia mola mucho"
	- Solo existen tres intentos
	- Si se pasan los tres intentos. Se despliega un mensaje informativo.
```
    // Tu solución
    
	Proceso clientes_autorizados
		
		clave<-"Fictizia mola mucho"
		numIntentos<-1
		totalIntentos <-3
		
		Mientras numIntentos<=3 Hacer
			Escribir "Introduce tu clave"
			Leer tuClave
			
		
			Si tuClave=clave Entonces
				Escribir "Bienvenido a Fictizia !!!"
				numIntentos<-4
			Sino
				
				Si numIntentos=totalIntentos Entonces
					Escribir "Lo sentimos, no dispones de más intentos"
				Sino
					Escribir "Sigue probando, te quedan " totalIntentos-numIntentos " intentos"
				Fin Si
				
				numIntentos<-numIntentos+1
				
			Fin Si
			
			
			
		Fin Mientras
		
		
	FinProceso
    
    
```




10 - Diseña un algoritmo que confirme si una fecha es valida y además devuelva la fecha en dos formatos diferentes.
- Características:
	- El usuario introduce tres números (día, mes, año)
	- Validar la fecha. En caso de error incluir un mensaje informativo.
	- Después de validar, devolvemos la fecha en formato DD/MM/AAAA
	- Convertimos el número del mes, en el nombre del mes real y devolvemos la fecha en el siguiente formato ( DD de MES de AAAA)
```
    // Tu solución
    
	 Proceso Fechas
		
		//DIA
		Escribir "Introduce un número de día"
		Leer numDia
		
		//MES
		Escribir "Introduce un número de mes"
		Leer numMes
		
		//AÑO 
		Escribir "Introduce un número de año"
		Leer numAnyo
		
		fechaValida<-Verdadero
		
		Si numDia>=1 & numDia<=31 & numMes>=1 & numMes<=12  Entonces
			
			Segun numMes Hacer
				1:
					mes<-'enero'
				2:
					mes<-'febrero'
					// Si es año bisiesto 29 días por el contrario 28 dias
					//Algoritmo cáculo de año bisiesto
					Si (numAnyo % 4 = 0) & (numAnyo % 100 <> 0) |(numAnyo % 400 = 0) Entonces
						//Comprobamos si el número de día es bisiesto: 29 dias
						Si numAnyo>=1 & numDia<=29 Entonces
							//Fecha correcta
							Escribir "La fecha es correcta"
						Sino
							//Fecha incorrecta
							fechaValida<-Falso
						Fin Si
					Sino
						//No bisiesto 28 dias
						Si numAnyo>=1 & numDia<=28 Entonces
							//Fecha correcta
							Escribir "La fecha es correcta"
						Sino
							//Fecha incorrecta
							fechaValida<-Falso
						Fin Si
					Fin Si
				3:
					mes<-'marzo'
				4:
					mes<-'abril'
				5:
					mes<-'mayo'
				6:
					mes<-'junio'
				7:
					mes<-'julio'
				8:
					mes<-'agosto'
				9:
					mes<-'septiembre'
				10:
					mes<-'octubre'
				11:
					mes<-'noviembre'
					Si numMes>=1 & numMes<=30 Entonces
						Escribir "La fecha es correcta"
					Sino
						fechaValida<-Falso
					Fin Si
				12:
					mes<-'diciembre'
					
					Si numMes>=1 & numMes<=31 Entonces
						Escribir "La fecha es correcta"
					Sino
						fechaValida<-Falso
					Fin Si
					
				De Otro Modo:
					fechaValida<-Falso
				Fin Segun
			
		Sino
			fechaValida<-Falso
		Fin Si
		
		
		Si fechaValida Entonces
			Escribir numDia "/" numMes "/" numAnyo
			Escribir numDia " de " mes " de " numAnyo
			
		Sino
			Escribir "La fecha es incorrecta"
		Fin Si
		
		
	FinProceso
    
    
```

18 - Diseña un algoritmo introducido un numero y pasarlo a número romanos.
- Esperamos que el número sea menor de 50

![numeros_romanos](https://eloviparo.files.wordpress.com/2009/09/numeros-romans.jpg?w=466&h=172)

```
    // Tu solución
    
	Proceso Conversion_NumRomanos
		
		Escribir "Introduce un número del 1 al 50"
		Leer num
		
		Si num>=1 & num<=50 Entonces
			Escribir "El número introducido es correcto"
			
			
			unidades<-TRUNC (num MOD 10) 
			decenas<- TRUNC ( num / 10 )
			
			// Escribimos unidades y decenas
			Escribir "Decenas: " decenas " - Unidades: " unidades
			
			// UNIDADES
			Segun unidades Hacer
				1:
					letraUnidad<-'I'
				2:
					letraUnidad<-'II'
				3:
					letraUnidad<-'III'
				4:
					letraUnidad<-'IV'
				5:
					letraUnidad<-'V'
				6:
					letraUnidad<-'VI'
				7:
					letraUnidad<-'VII'
				8:
					letraUnidad<-'VIII'
				9:
					letraDecena<-'IX'
			Fin Segun
			
			
			// DECENAS
			Segun decenas*10 Hacer
				10:
					letraDecena<-'X'
				20:
					letraDecena<-'XX'
				30:
					letraDecena<-'XXX'
				40:
					letraDecena<-'XL'
				50:
					letraDecena<-'L'
			Fin Segun
				
				
			
			Escribir "Conversión del número " num " a número romano " letraDecena letraUnidad	
			
			
			
		Sino
			Escribir "El número introducido es incorrecto"
		Fin Si
		
	FinProceso

```