# Investigación: Algoritmo "Go to Point" Simple


| Código | Description |
| ------:| ----------- |
| ***Asignatura*** | Código del Trabajo o Número de Tarea | 
| **TSM-2024-I** | Tarea *01* |
| 
## Contenido

- [Objetivo](#objetivo)
- [Introducción](#introduccion)
- [Desarrollo](#desarrollo)
- [Autor](#autor)
- [Referencias](#referencias)

## Objetivo

Implementando un algoritmo de tipo *"go to goal"* mover un robot dada una posición inicial a un punto final.
## Introducción

Un algoritmo es un conjunto ordenado de operaciones sistemáticas que permite hacer un cálculo y hallar la solución de un tipo de problemas.
La pose de un robot se refiere a la descripción de la  posición y la rotación de un robot en el espacio. El robot Turtlebot3 es del tipo (2,0) por lo que sólo puede moverse en el plano, la Pose estará definida como la Posición (x, y) y su orientación como la Rotación θ de su eje Z.
Un robot *go to goal* es un robot móvil que puede avanzar y girar, este necesita mecanismos de locomoción que le permitan moverse dentro de un ambiente establecido.`[^1]` 


## Desarrollo

En algoritmo *Go to Goal* el objetivo es llegar a un punto deseado partiendo de un origen, en este caso se proponen las coordenadas. 


![MarineGEO circle logo](/images/42324.jpg "MarineGEO logo")

1. ¿Cuáles son las ventajas y desventajas de utilizar la función atan2?
Es una función que elimina la tarea de hacer los cálculos para obtener el ángulo deseado, sin embargo ésta sólo da el ángulo positivo, es decir, que si hubiera límites en los movimientos físicos del robot, existiría la posibilidad de causar un daño al motor ya que podría intentar llegar a una posición angular correcta pero dando un giro completo, por ejemplo.
2. ¿Cómo variaría el algoritmo si la orientación "θ" del robot al alcanzar el punto P1 fuera obligatoria? Habría que recalcular un alfa final con el método propuesto al inicio.
3. ¿A qué atribuye los errores de orientación y distancia que se producen durante el movimiento? A los factores físicos que se ignoran en una simulaición, como lo pueden ser la fricción de las llantas con el suelo, que hagan que éstas varíen su posición durante el trayecto al punto deseado.

***Bloques de código***

El código propuesto usando el algoritmo *"Go to Goal"* es el siguiente:

``` py

import math
def main():
    #Posición inicial (supuestas)
    P0=(2,2)
    theta=math.pi /2
    #Posición final (supuestas)
    P1=(5,7)

    #Paso 1
        #Calcular alfa para girar el robot hacia donde se moverá linealmente
    theta2=math.atan2(P1[1]-P0[1],P1[0]-P0[0])
    alfa=theta-theta2

    #Paso 2
        #Avanzar al robot en x relativo (del robot) hacia punto final
    x=math.sqrt((P1[1]-P0[1])**2 + (P1[0]-P0[0])**2)
    

    return 0
```


## Autor
**Autor** Moreno Cedano Ruth Getzemaní [GitHub profile](https://github.com/ruthmced)

## Referencias

[^1]: Othman, Abdulghafar & Mohammed, Saad & Kanhan, Nuraddin & Mohammed, Khalil & Ahmed Asinger, Ahmed. (2019). Go to Goal Robot. 10.13140/RG.2.2.21982.92481. 

