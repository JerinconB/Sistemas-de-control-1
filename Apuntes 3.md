# Apuntes sistemas de control 1 - Tercer corte
### Rincon Benavides Juan Esteban 
### Avila Rojas Nestor Alexander
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

## Metodo modificado por miller 
El método modificado por Miller es una variación del método de la recta tangente de Ziegler & Nichols, diseñada para mejorar la sintonía de controladores PID en sistemas con retardo (tiempo muerto), pero buscando una respuesta más suave y estable, especialmente en la industria.

En este caso miller propone que la recta debe pasar tal cual como en el primer metodo mas sinembargo la constante de tiempo se identificara apartir de un valor fijo el cual sera del 63.2% del valor final de la grafica  teniendo asi las mismas ecuaciones pero cambia el valor de $t_m$

[![image.png](https://i.postimg.cc/tJj2J3Z5/image.png)](https://postimg.cc/YGd1ymxG)

Son métodos muy antiguos en tiempos donde no setenían ayudas computacionales y la electrónica ycomputación a penas estaban naciendo

Dentro de ese contexto estos métodos hicieron una revolución ya que permitían evadir el modelamiento matemático riguroso

Se convirtieron en un paradigma de la identificación de sistemas y hoy en día todavía se proponen métodos siguiendo esta filosofía

## Metodo de identificacion de 2 puntos (Primer orden) 
Debido a las impresiciones que son inherentes a los métodos que involucran recta tangente (Métodos de un punto), los métodos de 2 puntos permiten una mejor representación de la respuesta del modelo ya que hay 2 puntos de referencia para su aproximación.

Existe gran variedad de métodos de 2 puntos, todos se aplican igual lo que cambian son las constantes del método

[![image.png](https://i.postimg.cc/4xmbJL2G/image.png)](https://postimg.cc/WdcJ8nPY)

Estos metodos se podrian decir que son mas cencillos pues ya tenemos conocimiento de la gran mayoria de incognitas y son mas lineales pues solo requerimos de la tabla y las ecuaciones a realizar las cuales son 

$$\tau = A t_1 + B t_2$$

$$t_o = C t_1 + D t_2$$

$$K = \frac{\Delta y}{\Delta u}$$

y la table con diferentes autores es la sigiente cada uno de los autores tiene sus porcentajes y constantes diferentes unas mejores que otras 

[![image.png](https://i.postimg.cc/W4S2X8jD/image.png)](https://postimg.cc/CZBTKjRY)

## Ejemplo aplicando el metodo de Smith por 2 puntos 
Para este metodo pue lo que deberemos hacer es teniendo en cuenta los porcentajes nombrados por Smith para los 2 puntos correspondientes, elvalor final de la grafica y los valores de las constantes A,B,C y D podremos hallar el controlador, entonces:

[![image.png](https://i.postimg.cc/CxxYdDbS/image.png)](https://postimg.cc/2VMgK1HK)

[![image.png](https://i.postimg.cc/Pf1d7dts/image.png)](https://postimg.cc/145xnhnJ)

Para el valor final que es 2 los valores de P1 y P2 son:

$$P_1=2*0.283=0.566$$

$$P_2=2*0.632=1.260$$

Sabiendo el valor de estos dos puntos podremos hallar el tiempo en el cual estas estos mismos y ese tiempo es:

[![image.png](https://i.postimg.cc/cCF9zKCB/image.png)](https://postimg.cc/7JTnGZg5)

Con estos dos tiempos podremos comenzar a calcular las ecuaciones mencionadas anteriormente para asi poder hallar K y la funcion de transferencia del sistema controlado

$$\tau = (-1{,}5)(1{,}67) + (1{,}5)(2{,}89) = 1{,}83\ \text{segundos}$$

$$t_o = (1{,}5)(1{,}67) + (-0{,}5)(2{,}89) = 1{,}06\ \text{segundos}$$

$$K = \frac{2 - 0}{1 - 0} = 2$$

$$G(s) = 2 \ast \frac{e^{-1{,}06s}}{1{,}83s + 1}$$

ya con esto lo podremos graficar y darnos cuenta el comportamiento que tiene tanto la curva de reaccion como el modelo que acabamos de hallar 

[![image.png](https://i.postimg.cc/Yq4z7DsH/image.png)](https://postimg.cc/56VCqgJ7)

## Metodo de identificacion de 2 puntos (Segundo orden) 
Con los métodos de 2 puntos También es posible obtener funciones de transferencia de Segundo orden más tiempo muerto, la aplicación es igual pero cambian las constantes y en este caso cambia el autor a analizar en este caso es por Viteckova.

La fucnion de transferencia tambien cambia pues aumentamos de grado quedando de la siguiente forma:

$$G(s) = \frac{k e^{-t_o s}}{(\tau s + 1)(\tau s + 1)}$$

## Ejemplo aplicando método de Viteckova
Para este ejemplo utilizaremos la grafica vista anteriormente en el metodo de Smith su valor final sera de 2 y su tabla es la sigiente.

[![image.png](https://i.postimg.cc/SKZGk0km/image.png)](https://postimg.cc/XZC5kzrP)

Teniendo un valor final de 2 los puntos son:

$$P_1=2*0.7=1.4$$

$$P_2=2*0.33=0.66$$

Graficando esos 2 puntos tenemos los sigientes tiempos para T1 y T2 

[![image.png](https://i.postimg.cc/vmDV74wd/image.png)](https://postimg.cc/cKyC04JD)

Con estos dos tiempos podremos comenzar a calcular las ecuaciones mencionadas anteriormente para asi poder hallar K y la funcion de transferencia del sistema controlado

$$\tau = (-0{,}749)(1{,}81) + (0{,}749)(3{,}29) = 1{,}1\ \text{segundos}$$

$$t_o = (1{,}937)(1{,}81) + (-0{,}937)(3{,}29) = 0{,}423\ \text{segundos}$$

$$K = \frac{2 - 0}{1 - 0} = 2$$

$$G(s) = \frac{2 \ast e^{-0{,}423s}}{1{,}21s^2 + 2{,}2s + 1}$$

Y como resultado final veremos la grafica correspondiente a cada curva 

[![image.png](https://i.postimg.cc/cLLgZvH8/image.png)](https://postimg.cc/vcCHtH5Q)

## Validez de los modelos empíricos
El modelo se obtiene para un determinado punto de operación del Sistema, si el sistema no es lineal (como la mayoría de procesos) se requerirá un modelo diferente para cada punto de operación

[![image.png](https://i.postimg.cc/m22210Gv/image.png)](https://postimg.cc/23MfP9yG)

## Identificación sistemas inestables
### Lazo abierto 
Algunos sistemas inestables se pueden identificar en lazo abierto, por ejemplo un motor es inestable en posición, el modelo que se obtiene es aproximado. El margen de
error es asumido por el controlador

## Aproximación FOPDTI
Primer orden más tiempo muerto con factor integrante

El modelo para aproximar es:

$$G = \frac{K e^{-s t_o}}{(\tau s + 1)s}$$

Metodología

• Se captura curva de reacción en lazo abierto

• Se deriva la curva obtenida (numéricamente o simulación)

• El resultado se aproxima a primer orden más tiempo muerto
(métodos ya vistos)

## Ejemplo

[![image.png](https://i.postimg.cc/KzzJMGJK/image.png)](https://postimg.cc/hJkLFBFg)

# Diseño de controladores PID en lazo abierto --- 27/05/2025
Un control PID de lazo abierto es un sistema de control que aplica una acción de control calculada (basada en un modelo matemático o una entrada predeterminada), sin usar retroalimentación de la salida real del sistema, el controlador no mide la salida real del proceso para corregir errores solo actúa en función de la señal de referencia o condiciones conocidas.

## Acciones de control 
### Proporcional 
La acción de control proporcional es la parte del controlador PID que responde directamente al valor del error actual entre la referencia deseada y la salida real del sistema, su función es corregir el error de forma inmediata y proporcional a su magnitud.

$$u(t) = K_p * e(t)$$

$$U(S) = K_p * E(S)$$

### Integral
Calcula el error acumulado, de tal manera que cuando el error tiende a cero el incremento en la acción de control Tambien se va hacienda mas pequeña hasta llegar a cero.

$$u(t) = K_i \int e(t)\,dt$$

$$U(s) = K_i \ast \frac{E(s)}{s}$$

Su diagrama de bloques es el siguiente:

[![image.png](https://i.postimg.cc/jdZ9C1sk/image.png)](https://postimg.cc/w7RFG0Rh)

### Derivativa 
Debido a la medida de variación que da la derivada, esta acción de control se opone a las variaciones del error en el sistema

$$u(t) = K_d \ast \frac{de(t)}{dt}$$

$$U(s) = K_d \ast sE(s)$$

[![image.png](https://i.postimg.cc/XJf1WHHL/image.png)](https://postimg.cc/0MN0dfqK)

## Arquitecturas PID
• Se denomina arquitectura PID a las diferentes formas de combinar las 3 acciones de control Proporciona – Integral – derivativa

• Existen muchas formas de combinar las acciones de control, se explicarán las 3 mas clásicas

### Arquitectura paralela
La arquitectura paralela es una de las formas más comunes de implementar un controlador PID. En esta estructura, las tres acciones —proporcional (P), integral (I) y derivativa (D) se calculan por separado y luego se suman para formar la señal total de control.

[![image.png](https://i.postimg.cc/vm9372sy/image.png)](https://postimg.cc/GBLFdQtg)

[![image.png](https://i.postimg.cc/SxYrq1j9/image.png)](https://postimg.cc/VJ1MWRqs)

$$u(t) = K_p e(t) + K_i \int e(t)\,dt + K_d \frac{de(t)}{dt}$$

$$U(s) = K_p E(s) + K_i \frac{E(s)}{s} + K_d \ast s \ast E(s)$$

## Arquitectura ideal
La arquitectura ideal de un controlador PID (también llamada forma estándar o forma factorizada) representa el controlador como un único bloque que agrupa las acciones proporcional, integral y derivativa dentro de una expresión multiplicada por la ganancia proporcional $K_p$

[![image.png](https://i.postimg.cc/3RzGLYCb/image.png)](https://postimg.cc/47bnyC0z)

$$u(t) = K_p \left( e(t) + \frac{1}{T_i} \int e(t)\,dt + T_d \frac{de(t)}{dt} \right)$$

$$U(s) = K_p \left( E(s) + \frac{1}{T_i} \frac{E(s)}{s} + T_d \ast s \ast E(s) \right)$$

## Arquitectura Serie
La arquitectura en serie es una forma de implementar el controlador PID en la que las acciones proporcional, integral y derivativa están organizadas secuencialmente (en cascada), es decir, una salida alimenta a la siguiente.

[![image.png](https://i.postimg.cc/1XZtntKP/image.png)](https://postimg.cc/LYNRGm70)

$$u(t) = \frac{1}{T_i} \int \left( \left( e(t) + T_d \frac{de(t)}{dt} \right) K_p \right) dt$$

$$U(s) = \left( \left( E(s)(1 + T_d \cdot s) \right) K_p \right) \left( 1 + \frac{1}{T_i \cdot s} \right)$$

## Equipos para control PID

[![image.png](https://i.postimg.cc/nVY7Kb9T/image.png)](https://postimg.cc/qgqz0FLC)

Estos equipos estan diseñados para analizar y crear el control solo con darles los parametros iniciales, esto facilita mucha a la hora de realizar una sintonizacion pues ahorra pruebas y tiempo ademas de que pueden manejar varios lazos ala vez depende de su modelo hay unos que controlan hasta 20 lazo como otros los mas simples que son de lazo unico, estos equipos pueden tambien programarce desde sus botones o por medio de sofware com el TIA Portal etc...

[![image.png](https://i.postimg.cc/MKHTnh7n/image.png)](https://postimg.cc/2VpmJ9XY)

## Sintonización por prueba y error
La metodología más frecuente es:

• Ajustar a 0 las ganancias integral y derivativa

• Aumentar la ganancia proporcional hasta obtener el tiempo de establecimiento deseado

• Aumentar la ganancia integral hasta conseguir el sobre impulso deseado

• Aumentar la ganancia derivativa hasta reducir las oscilaciones al comportamiento deseado

• Ajustar de nuevo la ganancia proporcional

• Hacer ajuste fino de las otras ganancias

## Funciones de costo más utilizadas

$$IE = \text{Integral del error} = \int e(t)\,dt$$

$$ISE = \text{Integral del erroral cuadrado} = \int e(t)^2\,dt$$

$$IAE = \text{Integral del erroral absoluto} = \int |e(t)|\,dt$$

$$ITAE = \text{Integral del erroral absoluto por el tiempo} = \int (|e(t)| \cdot t)\,dt$$

Su representacion grafica es la siguiente:

[![image.png](https://i.postimg.cc/k45rjdX8/image.png)](https://postimg.cc/WDxf3CZb)

## Métodos de sintonización de lazo abierto
### Ziegler & Nichols
Es el primer método de este tipo para la sintonización de controladores PID, este método utiliza los parámetros de primer orden más tiempo muerto obtenidos en la identificación por curvas de reacción, el objetivo principal de este método es garantizar que la segunda oscilación de la respuesta sea $1/4$ del máximo pico, como veniamos trabajando anteriormente estos personajes asi como muchos otros tienen ya sus calculos respectivos para hallar el controlador deseado en este caso la tabla es:

[![image.png](https://i.postimg.cc/bJ553D5c/image.png)](https://postimg.cc/njvTLzZ0)

[![image.png](https://i.postimg.cc/8CfDDGVS/image.png)](https://postimg.cc/4KGjbrdL)

## Método por coeficiente de ajustabilidad
El método por coeficiente de ajustabilidad es una técnica empírica y simplificada para sintonizar controladores PID, usada especialmente en la industria, se basa en definir un parámetro llamado coeficiente de ajustabilidad (y) y a partir de él se determinan los parámetros del PID.

$$\gamma = \frac{t_m}{\tau}$$

[![image.png](https://i.postimg.cc/vmnRkvW8/image.png)](https://postimg.cc/069HJDWh)

## Método Smith (PID)
[![image.png](https://i.postimg.cc/7Zpd3TjF/image.png)](https://postimg.cc/SnfgqjSd)

# Diseño de controladores PID en lazo cerrado --- 3/06/2025
## Lazo cerado 
La idea central de estos métodos es identificar parámetros característicos de la dinámica del Sistema realizando pruebas en lazo cerrado, a partir de las pruebas en lazo cerrado se diseña el controlador PID
### Método de Ziegler & Nichols
1. Llevar las ganancias PID a cero (0)

2. Variar (aumentar) la ganancia proporcional (Kp) hasta que la salida del Sistema se comporte marginalmente estable

3. Medir el periodo de la oscilación obtenida, al cual se le llamará period ultimo $P_u$

4. La ganancia a la cual se logró el estado marginalmente estable se denomina ganancia última $K_u$

### Ejemplo 
$$G = \frac{1}{s^3 + 6s^2 + 11s + 6}$$

La prueba es en lazo cerrado entonces:

$$G_0 = \frac{K_p \cdot \frac{1}{s^3 + 6s^2 + 11s + 6}}{1 + K_p \cdot \frac{1}{s^3 + 6s^2 + 11s + 6}} = \frac{K_p}{s^3 + 6s^2 + 11s + 6 + K_p}$$

Para obtener las características de la respuesta marginalmente estable se busca cuando la parte real e imaginaria de la función de transferencia son cero (0):

$$s = j\omega$$

$$G_0 = \frac{K_p}{(j\omega)^3 + 6(j\omega)^2 + 11(j\omega) + 6 + K_p}$$

Se separa parte real e imaginaria en el denominador:

$$(j\omega)^3 + 6(j\omega)^2 + 11(j\omega) + 6 + K_p$$

$$j\omega((j\omega)^2 + 11) + (6(j\omega)^2 + 6 + K_p)$$

Para hallar la frecuencia de oscilación se iguala a cero la parte imaginaria:

$$j\omega((j\omega)^2 + 11) + (6(j\omega)^2 + 6 + K_p)$$

$$j\omega((- \omega)^2 + 11) + (6(-\omega)^2 + 6 + K_p)$$

$$- (\omega)^2 + 11 = 0$$

$$\omega = \sqrt{11}$$

$$P_u = \frac{2\pi}{\sqrt{11}} = 1.894\ \text{segundos}$$

Se iguala a cero la parte real para obtener la ganancia que produce el estado marginalmente estable:

$$j\omega((j\omega)^2 + 11) + (6(j\omega)^2 + 6 + K_p) \quad \Rightarrow \quad j\omega((-\omega)^2 + 11) + (-6(\omega)^2 + 6 + K_p)$$

$$-6\omega^2 + 6 + K_p = 0$$

$$K_p = 6\omega^2 - 6$$

$$K_p = 6(11) - 6 = 60 = K_u$$

Con los resultados obtenidos podemos comenzar a realizar las ecuaciones para el desarrollo del controlador segun las operaciones de la tabla 

[![image.png](https://i.postimg.cc/rsKBT6b4/image.png)](https://postimg.cc/y3CQhG76)

## Método del Rele
El método del relé, es una técnica experimental y automática para estimar los parámetros del sistema y diseñar controladores PID sin necesidad de conocer el modelo matemático del proceso.

Evita tener que subir excesivamente la señal de control para lograr la oscilación sostenida, Se puede manipular la respuesta obtenida durante la prueba a diferencia del método de Ziegler & Nichols

## Metodología
1. Medir el tiempo necesario para obtener estado estacionario en el Sistema en lazo abierto
2. Cerrar el lazo utilizando como controlador un Relé con histéresis
3. Capturar la salida obtenida (Oscilación sostenida)
4. Medir el period último (Pu) y la amplitud del ciclo último (Au)
5. Determinar la ganancia crítica Kc
6. Determinar la ganancia estática

## Diagrama de bloques

[![image.png](https://i.postimg.cc/k5L1SVh2/image.png)](https://postimg.cc/mcNyfr44)

[![image.png](https://i.postimg.cc/CLJcNrQT/image.png)](https://postimg.cc/kB6NMsCf)

La ecuacion correspondiente para poder realizar las operaciones segun la tabla es la sigiente, hay que tener en cuenta que se puede usar siempre que el maximo sobre impulso sea menor al 10%

[![image.png](https://i.postimg.cc/Yq4x62Yg/image.png)](https://postimg.cc/7fk7DkBY)

[![image.png](https://i.postimg.cc/qqN2xQh0/image.png)](https://postimg.cc/kRdVnQvh)

## Fenómeno Wind-up
El fenómeno de Wind-up (también llamado integral windup o rebose del integrador) ocurre cuando la acción integral del controlador PID se acumula en exceso debido a que la salida del controlador está saturada (limitada) y no puede seguir aumentando o disminuyendo.

[![image.png](https://i.postimg.cc/rmPrsWhH/image.png)](https://postimg.cc/342RbyQj)

## Anti wind-up por saturación de la acción integral

[![image.png](https://i.postimg.cc/cH2BjVN6/image.png)](https://postimg.cc/7G1zJthy)

La acción integral seguirá acumulando

Los tiempos de respuesta del Sistema se seguirán viendo afectados

Se proteje el actuador

## Anti wind-up por integración condicional

[![image.png](https://i.postimg.cc/J4Wbk37w/image.png)](https://postimg.cc/5jnYcCFp)

Se soluciona el problema del tiempo de respuesta del sistema

Se producen algunos pulsos no deseados en la respuesta del sistema debido a la suspensión abrupta de la acción integral

## Anti wind-up por recálculo y seguimiento
