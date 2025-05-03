# Corrección parcial 1 
## Punto 1
La figura representa un Sistema para variar la posición de un émbolo. La bomba de presión es controlada por tensión v(t) que genera una presión p(t); la tensión de entrada de la bomba es suministrada por un amplificador que a 0 V entrega a la bomba 0 V y tiene una salida de 10 V con una entrada de 1 V. El émbolo de M = 5 Kg y área de contacto con el fluido de 0.25 m², se mueve dentro de la carcasa con un rozamiento viscoso de 2.5 N/m/s. El émbolo está en contacto con un cuerpo elástico con constante de elasticidad de 1 N/m. El fabricante de la bomba indica en su datasheet que puede ser modelada a través de una ecuación diferencial, donde la suma de la presión y la tasa de cambio de la presión es equivalente a aplicar 1.2 veces la entrada.

[![image.png](https://i.postimg.cc/cCp5bkt4/image.png)](https://postimg.cc/LgVTqTVr)

Para la solución del siguiente ejercicio deberemos analizar el sistema en 2 grupos uno en el cual se vea el sistema neumático y el segundo el sistema de la caja en movimiento por el mismo teniendo que para el sistema en general del modelo neumático tendremos lo siguiente.

$$p(t) + p'(t) = 1.2 \, v(t)$$

$$\frac{v(t)}{c(t)} = \frac{0 - 10}{0 - 1} = 10$$

$$p(t) + p'(t) = 12 \, c(t)$$

$$p + s p = 12 \, e$$
Teniendo esto damos por finalizado a la primera parte del ejercicio la segunda es analizar la parte de la masa para ver y sacar sus segundas ecuaciones teniendo que el diagrama de cuerpo libre correspondiente para la masa es el siguiente.

[![image.png](https://i.postimg.cc/15KjHB5P/image.png)](https://postimg.cc/xcc5jKzF)

Su representación matemática es la siguiente.

$$F_k + F_x - F = M \ddot{y}$$

$$y + 2.5 \dot{y} - p(t) A = 5 \ddot{y}$$

## Punto 2
Se tiene un sistema intercambiador de calor que tiene una electroválvula que permite cambiar el paso de vapor para cambiar la temperatura del horno. Se está realizando el modelamiento de la parte driver-electroválvula y se obtiene la función de transferencia de la figura. Grafique la respuesta de dicho conjunto para una entrada de 4.2 V, sabiendo que el flujo q está en cm³/s y la base de tiempo está en segundos. Señale toda la información relevante (vista en clase) en la gráfica.

[![image.png](https://i.postimg.cc/gjsHvMyT/image.png)](https://postimg.cc/MfcBwmF7)

A continuación nos piden graficar la respuesta de dicho conjunto para una entrada de 4.2 voltios hoy sabiendo que tenemos un flujo k específico y el tiempo estará en segundos para ello lo que resultará más fácil es analizar lo siguiente sabiendo que Q es el flujo y V es el voltaje, aremos las siguientes operaciones matemáticas
La función de transferencia del sistema es:

$$\frac{Q}{V} = \frac{2805.56}{s + 100}$$

Reescribiendo:

$$\frac{2805.56}{100} \cdot \frac{1}{\frac{s}{100} + 1} = \frac{28.05}{\frac{s}{100} + 1}$$

Respuesta final para una entrada de 4.2 V:

$$V_{\text{final}} = 28.05 \cdot 4.2 \, \text{V} = 117.81 \approx 119.7$$

Constantes del sistema:

$$\tau = \frac{1}{100} = 0.01$$

$$T_s = 0.04$$

Con estos resultados hoy podemos identificar mejor las partes de la gráfica y dar una respuesta al ejercicio teniendo que la gráfica correspondiente al en la transferencia de la figura es la siguiente

[![image.png](https://i.postimg.cc/2j0W7BRM/image.png)](https://postimg.cc/LhZhH5s3)

# Sistemas de segundo orden 

