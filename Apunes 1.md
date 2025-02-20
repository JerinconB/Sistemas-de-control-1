# Modelamientos de Sistemas 
El modelamientos de sistemas de control es uno de los pasos mas importantes para un b uen analisis y diseño en sistemas de control, pues este nos ayuda a representar por medio de las matematicas yn comportamiento dinamico de algun sistema en especifico meduante ecuaciones, estas asu vez nos ayudan a ver el cambio de sus variables a travez del tiempo.
## Principio General del Modelamiento
Como se dijo anteriomente el modelamiento de un sistema consiste en representarlo mediante un conjunto de ecuaciones o relaciones matematica con el fin de describir su comportamiento atraves del tiempo para si poder analizar y predecir como va a responder ante diferentes condiciones para ello varios de los principos son:
### Conservacion de leyes fundamentales como:
Leyes de Newton (para sistemas mecánicos),
Leyes de Kirchhoff (para circuitos eléctricos),
Leyes de conservación de masa, energía y momento.
### Causalidad 
Esta establece la relacion etre casusa y efecto donde influyen tanto las entradas como las salidas del sistema anlizado esto atraves de unos procesos internos.
### Linialidad o no linialidad 
Esto  nos dira si el sistema se comporta de forma lineal en el tiempo o no ya que pueden haber sistemas los cuales cambien demaciado su estructura durante el transcurso del mismo.
## Como lucen los modelos de ecuaciones diferenciales
Estos son conbinaciones de derivadas de difernte orden su exprecion general esta dada de la siguiente forma:

$$a_{1}\frac{\partial^2 f }{\partial t^2}+a_{2}\frac{\partial f}{\partial t}+a_{3}f=u(t)$$

Donde F es la salida del Sistema,U es la entrada del Sistema,La solución no es un número es una función, gracias a este tipo de funciones podemos ver y analizar los sistemas.

## Sistemas Mecanicos 
Son aquellos sistemas que estan diseñados con utencilios como resortes, amortiguadores, estos a su vez conectados a una masa o superficie, son sistemas los cuales no llevan nada electrico y aparte de eso tambien pueden ser rotativos o combinados su escructura es:

[![Captura-2.png](https://i.postimg.cc/pX1BmMnw/Captura-2.png)](https://postimg.cc/HVXMNKzz)

Para el analizis de estos sistemas nos vasamos en fenomenos fisicos tales como la ley de hooke:

$$F_{R}=K*x$$

La friccion viscosa 

$$F_{f}=b*v_{m}$$

y las leyes de newton 

$$F=m*a$$

Para la solucion de los ejercicios se empesara con el analizis para asi saber como comenzaremos las ecuaciones, para el caso de un sistema de masa resorte amortiguador aplicaremos el diagrama de cuerpo libre para la masa y a si vmermos las fuerzas aplicadas para la ecuacion para la imaguen anterior es como se muestra a continuacion:

[![Captura-de-pantalla-2025-02-16-153035.png](https://i.postimg.cc/4317hpSY/Captura-de-pantalla-2025-02-16-153035.png)](https://postimg.cc/VSdLx01w)

Aqui observamos la sumatoria de furzas igualadas ala masa por su aceleracion, la ley de newton una vez con ella pasaremos a remplazar los valores de las fuerzas aplicadas como u(t), $F_{b}$ y $F_{k}$ para asi obtener la funcion del sistema como lo vemos en la imagen.

## Sistemas Mecanicos mas Complejos 
Los sistemas mecanicos mas complejos son aquellos constituidos por uno o mas sistemas mecanicos juntos su analicis suele ser mas complicado pero no difiere mucho de los calculos para un sistema mecanico simple, para ello veremos un pequeño ejemplo de un sistema mecanico mas complejo.

[![Captura-de-pantalla-2025-02-17-123512.png](https://i.postimg.cc/nLk8bLX8/Captura-de-pantalla-2025-02-17-123512.png)](https://postimg.cc/Ny5CRB8b)

En la imguen podemos ver dos masas conectadas a un resorte entre si y un resorte para la masa 1 y dos amortiguadores para la masa 2.
Para el analizis del ejemplo empesaremos analizando el sistema por medio de un diagrama de cuerpo libre con el fin de ver las fuerzas que actuan en cada mas, una vez con esto veremos que nos queda de la siguiente forma:

[![Captura-de-pantalla-2025-02-17-132632.png](https://i.postimg.cc/7L3n6G46/Captura-de-pantalla-2025-02-17-132632.png)](https://postimg.cc/TyPDNPpM)

Una vez con esto podremos sacar las funciones correspondientes a cada masa empezaremos con la masa numero 1, por medio de la ley de newton veremos la sumatoria de fuerzas la cual luego remplazaremos con las ecuaciones correspondientes como veremos en la siguiente imagen.

[![Captura-de-pantalla-2025-02-17-133053.png](https://i.postimg.cc/xjw3SDBg/Captura-de-pantalla-2025-02-17-133053.png)](https://postimg.cc/9zB7GSmq)

Una vez calculada la masa 1 pasaremos a los calculos de la masa 2 en este caso no varia mucho mas haya de que tenemos en este caso dos amortiguadores agarrados ala pared y el resorte en medio sabiendo esto la funcion que describe las fuerzas de la masa 2 quedaria de esta forma:

[![Captura-de-pantalla-2025-02-17-133734.png](https://i.postimg.cc/Zn6WPgbx/Captura-de-pantalla-2025-02-17-133734.png)](https://postimg.cc/5QN9bsFX)

## Sistemas Rotacionales 
Son otro tipo de sistemas mecanicos solo que en este caso lo que varia es la fuerza aplicada ya que es un movimiento circular que nos genera un torque,estos sistemas se analizan usando las leyes del movimiento rotacional, que son parecidas a las del movimiento traslacional pero en términos angulares.

[![Captura-de-pantalla-2025-02-17-135557.png](https://i.postimg.cc/WzV5wBm2/Captura-de-pantalla-2025-02-17-135557.png)](https://postimg.cc/Q96gXnnP)

Para el anaisis de estos sistemas usaremos leyes comparables al movimiento lineal tales como la fuerza de rosamiento donde el angulo $\varphi$ es el angulo de torcion.

$$F_{r}=k*\varphi$$

Tambien tendremos la fuerza de friccion donde la $\frac{\mathrm{d}\varphi }{\mathrm{d} t}$ es la velocidad angular del sistema

$$F_{f}=b*\frac{\mathrm{d}\varphi }{\mathrm{d} t}$$

y por ultimo el torque donde la constante j es el momento de inercia del sistema 

$$T=j*\frac{\partial \varphi ^2 }{\partial t^2}$$

Deigual forma como se venia trabajando para los demas sistemas este tambien lo anamizaremos por medio de un diagrama de cuerpo libre el cual nos quedara de la siguiente forma ya con las fuerzas dibujadas para asi poder generar la funcion correspondiente.

[![Captura-de-pantalla-2025-02-17-141638.png](https://i.postimg.cc/zvnK03zM/Captura-de-pantalla-2025-02-17-141638.png)](https://postimg.cc/xN1Xdfby)

Una vez con esto podremos hacer la funcion teniendo que $\sum T=J*\alpha$ para ello tendremos que:

$$T-F_{R}-F_{F}=j*\alpha$$

Remplazando tendriamos que la funcion no quedaria de la siguiente forma.

$$T(t)-K\theta (t)-B\frac{\partial \theta(t)}{\partial t}=J\frac{\partial^2\theta (t) }{\partial t^2}$$

## Conversion Movimiento Translacional-Rotacional 
Para estos sistemas veremos el proceso mediante el cual se convierte un desplazamiento lineal en un desplazamiento angular o a la inversa todo esto mediante un sistema mecanico el cual puede ser desglosado en varias partes las mas comunes son:
### Poleas y correas
Transmiten movimiento rotacional a uno lineal o al contrario a través de una banda o varias bandas.
### Cremallera y piñón
Convierte el movimiento rotacional de un engranaje en movimiento lineal.
### Tornillos sin fin 
Convierte la rotación de un tornillo dada ya sea por un motor o un giro manual en movimiento lineal.

💡Ejemplo: Tenemos el siguiente sistema combinando el cual es un motor enganchado a una polea para a si poder mover la caja.

[![Captura-de-pantalla-2025-02-17-151255.png](https://i.postimg.cc/x18sfD9Z/Captura-de-pantalla-2025-02-17-151255.png)](https://postimg.cc/k2rNsH6N)

Teniendo esto como base pasaremos al diagrama de cuerpo libre obteniendo a si las fuerzas positivas y negativas del sistema.

[![Captura-de-pantalla-2025-02-17-151604.png](https://i.postimg.cc/zfWFvq6x/Captura-de-pantalla-2025-02-17-151604.png)](https://postimg.cc/SXSMtby9)

Con esto pasaremos a resolver la $\sum T=J*\alpha$ teniendo asi:

$$T_{m}-T_{1}-T_{F}=J_{m}*\alpha$$

Donde remplazando las incognitas por sus funciones obtendremos el siguiente resultado, sabiendo que para $T_{1}$ el momento de inercia es $mr^{^2}$.

$$T_{m}-mr^{^2}\frac{\partial^2\theta  }{\partial t^2}-B\frac{\partial \theta }{\partial t}=J_{m}\frac{\partial^2\theta  }{\partial t^2}$$

Teniendo en cuenta que el $\theta = y/r$ remplazamos en la ecuacion

$$T_{m}-mr\frac{\partial^2 y}{\partial t^2}-\frac{B}{r}\frac{\partial y }{\partial t}=\frac{J_{m}}{r}\frac{\partial^2 y}{\partial t^2}$$

## Circuitos RLC
Un circuito RLC es un circuito eléctrico que está formado por resistencias inductancias y capacitancias estas a su vez están conectadas en serie o en paralelo también pueden ser circuitos mixtos son fundamentales para los sistemas de control filtrado de señales y otros circuitos electrónicos.

[![Captura-de-pantalla-2025-02-20-135413.png](https://i.postimg.cc/SRD1vHG4/Captura-de-pantalla-2025-02-20-135413.png)](https://postimg.cc/D44cWjDp)

Estos circuitos se rigen bajo la ley de ohm y otras leyes más como podemos ver en las siguientes ecuaciones tenemos que para cada uno de los elementos tenemos una ecuación característica estas son las siguientes

$$R=\frac{V(t)}{I(t)}$$
$$I=C\frac{\mathrm{d}V(t)}{\mathrm{d} t}$$
$$V=L\frac{\mathrm{d}i(t) }{\mathrm{d} t}$$

Teniendo en cuenta estas ecuaciones y la imagen anterior podemos resolver un ejemplo el cual sería la solución del circuito en serie, para ello utilizaremos la ley de voltajes de kirchhoff para así poder solucionar y encontrar la ecuación que nos describe el sistema.

Iniciaremos haciendo la suma de voltajes e igualando a cero.

$$-U+V_{R}+V_{L}+V_{C}=0$$

Luego reemplazaremos las ecuaciones mostradas anteriormente en la ecuación.

$$-U(t)+i(t)R+L\frac{\mathrm{d}i(t)}{\mathrm{d}t}+V_{C}=0$$

Una vez teniendo esto nos podemos dar cuenta que para que nos quede todo el factor es de voltaje del condensador reemplazaremos en la derivada de $i(t)$ por lo que vale $I$, teniendo la siguiente ecuación.

$$-U(t)+RC\frac{\mathrm{d}V_{C}(t)}{\mathrm{d} t}+LC\frac{\mathrm{d^2}V_{C}(t)}{\mathrm{d}t^2}+V_{C}=0$$


