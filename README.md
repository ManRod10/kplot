# kplot

Esta herramienta se diseño para facilitar la compresion de las técnicas estándar de evaluación de impacto. 
La aplicacion permite la visualizacion de 3 tecnias y del problema de variables omitidas, los tipos de visualizacion incluida son:

* **Variables Omitidas** *(omitida)*: Esta opcion permite elegir el tamaño de la muestra, el objetivo de esta opcion es mostrar como el
signo de una correlacion puede ser producto de la omision de una variable, ademas muestra como la inclusion de dicha variable
puede corregir el problema

* **Matching** *(psm)*: 
Esta opcion permite elegir el tamaño muestral y el capiler o el radio, a su vez muestra tres etapas del proceso, deteccion de
observaciones comparables, restriccion al soporte comun y estimacion del efecto, como un promedio.

* **Regresion Discontinua** *(rd)*:
Esta opcion permite visualizar el diseño, cuando se cuenta con una Rolling variable (o un puntaje de asignacion), entre los parametros 
a elegir estan el tamaño muestral y el ancho de la ventana. 

* **Diferencias en Diferencias** *(dd)*:
Esta opcion ....

## Instalacion 

Para instalar el comando se deben ejecutar estas dos lineas en Stata

```
net install github, from("https://haghish.github.io/github/")
github install ManRod10/kplot
```

## Ejemplos

la syntasis del comando es sencilla, algunas visualizaciones requieren uno o dos parametros, pero en general, en primer lugar va el tamaño muestran, mientras en la segunda posicion va el tamaño del caliper (radio) o el ancho de la ventana en el caso de RD.
para elegir el tipo de visualizacion basta con incluir en la opcion tipo() el modelo deseado. com


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
