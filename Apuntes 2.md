# Ecuaciones diferenciales de primer orden
## Funcion de transferencia
Las ecuaciones diferenciales de primer orden son las que hoy por lo general hoy la derivada de la función incógnita $y(x)$ aparece solo en la solución de su primera derivada

La estructura general de una ecuación de primer orden es la siguiente

$$a\dot{y}(t) + b y(t) = c u(t)$$

para hallar la solución defunción de transferencia tenemos que en primer paso aplicar Laplace teniendo así el siguiente resultado

$$asY(s) + bY(s) = cU(s)$$

Con esto podremos aplicar el concepto general de una función de transferencia la cual es despejar o tener todo en términos de la salida y la entrada

$$\frac{Y(s)}{U(s)} = \frac{c}{as + b}$$

Cómo podemos ver las funciones de transferencia de primer orden provienen de una ecuación diferencial de primer orden un ejemplo de ello sería el siguiente

$$\frac{Y(s)}{U(s)} = \frac{c}{as + b}$$

Dónde nos podemos dar cuenta que los parámetros a b y c hp son parámetros físicos del sistema que definen la dinámica del mismo
### Ejemplo
[![image.png](https://i.postimg.cc/fyPrbMrW/image.png)](https://postimg.cc/dZ8BHcFg)

Como podemos ver en el ejemplo primero hallaremos la ecuación general teniendo

$$a\dot{y}(t) + b y(t) = c u(t)$$

Luego de ello pasaremos a la forma general en la cual se hace una función transferencia

$$\frac{Y(s)}{U(s)} = \frac{c}{as + b}$$

A continuación veremos la ecuación que describe el sistema mostrado en la imagen el cual es un sistema hidráulico de un tanque con una resistencia o paso de agua

$$R_1 A_1 \frac{dh_1}{dt} = R_1 q_i - h_1$$

Con esto podemos darnos cuenta que deberíamos ser capaces de formar la función de transferencia del sistema teniendo en cuenta que
$$a = R_1 A_1$$
$$b = 1$$
$$c = R_1$$
Podemos reescribir la función de transferencia

$$\frac{H_1(s)}{Q_i(s)} = \frac{R_1}{R_1 A_1 s + 1}$$

## Forma canónica de los sistemas de primer orden
Ya sabemos en los apuntes anteriores como está definida la forma de transferencia de un sistema de primer orden, esta forma no permite identificar directamente los parámetros temporales del sistema para ello necesitamos el control que se prefiere de la forma canónica para ello necesitaremos hacer uno que otros cálculos los cuales son

$$\frac{Y(s)}{U(s)} = \frac{c}{as + b}$$

$$= \frac{\frac{c}{b}}{\frac{a}{b}s + 1}$$

Teniendo en cuenta esto consideramos que $\tau = \frac{a}{b}$ es una constante de tiempo y $K = \frac{c}{b}$ es la ganancia estática del sistema teniendo lo siguiente 

$$ \frac{Y(s)}{U(s)} = \frac{K}{\tau s + 1} $$

Con esto podremos retomar el ejemplo anterior y darnos cuenta que cambiando los parámetros podemos tener diferentes combinaciones que nos permiten evaluar características de la respuesta temporal del sistema
### Ejemplo 2 
Identificar el $\tau$ y $K$ del siguiente sistema 

$$\frac{Y(s)}{U(s)} = \frac{0.8}{s + 1}$$

Sabiendo lo anterior tenemos que $\tau=1$ segundo y la ganancia del sistema $K=0.8$

## Respuesta temporal de un sistema de primer orden 
Hay varias respuestas que podemos dar para un sistema de primer orden todo esto depende según la entrada la cual se le aplique al sistema así como hay varias salidas también tenemos varias entradas pues dependemos que el mismo tipo de entrada sea el mismo que el de salía para ello podremos comenzar aplicando uno de los estímulos más comunes el cual es la entrada tipo escalón

$$Y(s) = \frac{U(s)K}{\tau s + 1} = \frac{\frac{A}{s} K}{\tau s + 1}$$

para la gran mayoría de sistemas según su tipo de entrada deberemos darle solución en este caso aplicaremos fracciones parciales teniendo que al despejar C1 y C2 tenemos la siguiente solución

$$Y(s) = \frac{C_1}{s} + \frac{C_2}{s + \frac{1}{\tau}} = \frac{A K}{s} - \frac{A K}{s + \frac{1}{\tau}}$$

Para terminar necesitaremos aplicar la transformada inversa de Laplace teniendo como resultado el modelamiento y una ecuación para ver su comportamiento a través de ciertos tiempos

$$\mathcal{L}^{-1} \{ Y(s) \} = y(t) = AK \left( 1 - e^{\frac{-t}{\tau}} \right)$$

### Constante del tiempo del sistema
Sabiendo la respuesta de $y(t)$ podemos ver cómo actúa a través del tiempo la entrada y cuándo se estabiliza para un mejor análisis sabiendo que AK es una constante y va a ser el punto máximo al cual llegará nuestro sistema con esto podemos armar la siguiente tablita y ver cuál va a ser el tao o el tiempo de establecimiento mejor para aplicarlo
[![image.png](https://i.postimg.cc/rpdbv0nn/image.png)](https://postimg.cc/JyLPXnWZ)

Con esto podemos graficar y ver cómo actúa cada tiempo y así mismo vemos que por lo general desde los cuatro taos el sistema ya es completamente estable para analizarlo
[![image.png](https://i.postimg.cc/SsCPK0pc/image.png)](https://postimg.cc/WFp89Hz4)

Esta función es muy importante ya que con esta podemos analizar el tipo de respuesta para cualquier tipo de entrada en este caso daremos varios ejemplos como el de un sistema rampa y el sistema hipotético de impulso
