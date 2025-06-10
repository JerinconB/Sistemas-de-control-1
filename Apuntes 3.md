# Identificacion de sistemas por curvas de reaccion --- 13/05/2025
Este proceso es estrictamente necesario para poder sintonizar cualquier controlador, aparte existen multiples formas y metodos para poder hallar el modelo de alguna planta en espesifico tales como lo son 

-Modelo matematico (Ecuaciones diferenciales)

-Curvas de reaccion en lazo abierto

-Identificacion de parametros en lazo cerrado 

-Analicis de frecuencia y tecnicas de inteligencia computacional 

## Pocedimiento de sintonizacion 
En general para diseñar cualquier controlador es necesario conocer el comportamiento de la planta para escoger adecuadamente los parámetros, en estos casos los controladores PID no son la excepción estos tambien aplicanm, a nivel industrial no se utiliza un modelo riguroso de la planta esto depende de la persona la cual este diseñando o analizando la planta y cada una de esas personas utiliza una metodolia diferente y para eso hay metodologías que permiten obtener modelos aproximados

## Metodologías curvas de reacción en lazo abierto
Permiten obtener un modelo de primer orden más tiempo muerto, es decir:

$$G(s) = \frac{ke^{-s t_0}}{\tau s + 1}$$

donde:

$\tau$ → Constante de tiempo del sistema

$k$ → Ganancia estática del sistema

$t_0$ → Tiempo muerto

Es necesario obtener los parámetros tiempo muerto y constante de tiempo a partir de la respuesta temporal del sistema, son métodos muy utilizados en la industria

## Aplicación curvas de reacción en lazo abierto
Condiciones para su aplicación
El sistema debe ser estable en lazo abierto

El sistema debe tener un comportamiento sobre o críticamente amortiguado

Prueba para obtener la respuesta
Como su nombre lo indica, consiste en la aplicación de una entrada escalón y capturar los datos que se obtienen a la salida

La respuesta es capturada por medio de un osciloscopio, tarjeta de adquisición de datos o incluso un microcontrolador

[![image.png](https://i.postimg.cc/5NXntRTg/image.png)](https://postimg.cc/ykzFQvV3)

## Metodo de ziegler y nichols
El método de la recta tangente de Ziegler y Nichols es una técnica clásica para sintonizar controladores PID (Proporcional-Integral-Derivativo) a partir de la respuesta temporal de un sistema, especialmente cuando el sistema tiene una respuesta tipo escalón.

Determinar los parámetros del controlador PID por medio de dos puntos los cuales son tiempo muerto ($t_m$) y $\tau$:

$t_m =$ cruce de la recta tangente con el eje del tiempo 

$$\tau = \tau' - t_m$$

$$K = \frac{\Delta y}{\Delta u}$$

A partir de la respuesta al escalón del sistema sin controlar (planta) y el trazado de una recta tangente al punto de inflexión.

[![image.png](https://i.postimg.cc/3NspNn0f/image.png)](https://postimg.cc/N2xLP84R)

