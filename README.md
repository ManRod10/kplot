
# kplot

Esta herramienta se diseño para el Curso de **Evaluacion de Impacto** de la Maestria en Economia de la Univerisdad EAFIT. con la intencion de facilitar la compresion de las técnicas estándar de evaluación de impacto. Este algoritmo permite una clara visualizacion del problema de variables omitidas, matching, la regresion disontinua y diferencias en diferencias.

* **Variables Omitidas** *(omitida)*: Esta opcion permite elegir el tamaño de la muestra, el objetivo de esta opcion es mostrar como el
signo de una correlacion puede ser producto de la omision de una variable, ademas muestra como la inclusion de dicha variable
puede corregir el problema

* **Matching** *(psm)*: 
Esta opcion permite elegir el tamaño muestral y el capiler o el radio, a su vez muestra tres etapas del proceso, deteccion de
observaciones comparables, restriccion al soporte comun y estimacion del efecto, como un promedio. Esta tecnica supone que se ***la seleccion se da unicamente en variables observables***

* **Regresion Discontinua** *(rd)*:
Esta opcion permite visualizar el diseño, cuando se cuenta con una Rolling variable (o un puntaje de asignacion), entre los parametros 
a elegir estan el tamaño muestral y el ancho de la ventana. Esta tecnica supone que ***alrededor del corte las observaciones estan balanceadas***.

* **Diferencias en Diferencias** *(dd)*:
Esta opcion permite visualizar el diseño, cuando el tratamiento se realiza en algun periodo en el tiempo, lo que permite aplicar diferencias entre grupos y en el tiempo, lo que permite eliminar un numero importante de variables no observables, esta opcion solo requiere que se especifique el tamaño muestral. El uso de esta tecnica requiere del supuesto de ***tendencias paralelas***

## Instalacion 

Para instalar el comando se deben ejecutar estas dos lineas en Stata

```
net install github, from("https://haghish.github.io/github/")
github install ManRod10/kplot
```

## Ejemplos

la sintaxis del comando es sencilla, algunas visualizaciones requieren uno o dos parametros, pero en general, en la primera posicion va el tamaño muestran, en la segunda posicion va el caliper (radio) en el caso de PSM o el ancho de la ventana en el caso de RD.
para elegir el tipo de visualizacion basta con incluir en la opcion tipo() el modelo deseado. 


* **Visualizacion de variable omitida con 500 obs**    
```
kplot 500 , tipo(omitida)
```
* **Visualizacion de Matching con 200 obs y un caliper de 0.05**   
```
kplot 200 0.05 , tipo(psm)
```
* **Visualizacion de Regresion Discontinua con 200 obs y ancho de ventana de 0.5**    
```
kplot 200 0.5 , tipo(rd)
```
* **Visualizacion de Diferencias en Diferencias con 200 obs**   
```
kplot 200 , tipo(dd)
```
