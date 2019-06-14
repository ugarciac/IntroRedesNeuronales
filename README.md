## Introducción a las Redes Neuronales
## Contenido
- Introducción
- Semejanzas entre una neurona biológica y un perceptrón
- ¿Qué es una red neuronal?
- Ejemplo del funcionamiento de un perceptrón
- Referencias

### Introducción
¿Qué es una neurona artificial?
Dentro del campo de la Inteligencia Artificial son métodos de aprendizaje autómatico cuya finalidad es imitar los procesos biológicos de las redes neuronales de los organismos vivos(Orallo, Ferri, & Quintana, 2004).

## Comparación de una neurona biológica y una neurona Artificial

### Neurona Biológica

![NeuralB](/media/neurona.gif)
* Cuerpo Celular (Soma): Tiene como función principal sintetizar la mayoría de las proteínas que se encuentran en la neurona.
* Núcleo: Contiene el material genético en forma de cromosomas
* Dendritas: Son prolongaciones protoplasmáticas, cortas y ramificadas que surgen desde el cuerpo celular. Estas prolongaciones se sencargan de recibir y procesar los impulsos que llegan de otras neuronas para transmitirlas al cuerpo celular.
* Axón: Se trata de una prolongación caracterizada por ser única y larga, pues en algunas ocasiones tiende a medir 1 metro de longitud. Esta prolongación se origina en el área del cuerpo celular. Tiene como función extraer el impulso resultante desde cuerpo celular y transmitirlo a otra zona del sistema

La comunicación entre neuronas se llama sinapsis la cual se da en la terminación del axón y las dendritas de la siguiente neurona liberadno una sustancia, esta cambia el balance de iones (átomos cargados electrónicamente) entre el interior y el exterior de la membrana celular. Cuando este cambio alcanza un nivel umbral, este efecto se expande a través de la mebrana de la célula hasta el axón. Cuando alzanza al axón, se inicia un potencial de acción.

Cuando el potencial de acción alcanza la terminación del axón, causa diminutas burbujas quimicas llamadas vesículas que descargan su contenido en el salto sináptico.

### Neurona Artificial
En 1943 McCulloch & Pitts inspirandos en la neurona biológica desarrollarón un modelo artificial de una neurona. Esta idea fue retomada más tarde por Rosenblatt quien creó una estructura llamada perceptrón. El perceptrón es una estructura la cual poseé una o varias entradas, una función de activación y una salida. Es la aproximación más cercana a una neurona biológica.
Las entradas del perecptrón actúan como las dendritas o señales de entrada hacia la neurona. La función de activación realiza el papel del soma que decide en que momento disparar esa señal eléctrica y la salida modela al axón que al activarse envía información hacia las neuronas con las que se conecta.

![NeuralP](/media/perceptron.png)

¿Entonces qué es una red neuronal?

Entonces una red neuronal se compone de un conjunto de perceptrones interconectados entre si, generando así una red, la cual su estructura puede volverse tan compleja como nosotros lo deseemos. La estructura más sencilla se comforma de tres capas, una capa de entrada, una capa oculta y una capa de salida.

![RedNeuronal](/media/RedNeuronal.png)

## Ejemplo
Para entender cómo funciona un perceptrón, a continuación realizaremos una ejemplificación, en la que le enseñaremos al percpetrón a responder a las entradas de una compuerta AND, en donde dados 2 valores de entrada 1 y 2 (input 1 y 2) nos dé un valor de salida esperado (output).

La compuerta lógica AND realiza un producto booleano dadas dos entradas, la condición que debe cumplir la compuerta AND es definida por la siguiente tabla de verdad.

| Entrada A| Entrada B | Salida |
| ---------|-----------| ------:|
|   0      |    0      |   0    |
|   0      |    1      |   0    |
|   1      |    0      |   0    |
|   1      |    1      |   1    |

## Flujo del funcionamiento
![PerceptronE](/media/PerceptronE.png)

#### Caso 1: Entrada 0, Entrada 0 ----> Salida 0
1. Se toman 2 entradas Entrada 0, Entrada 0, el tercer parámetro denominado bias es un valor de sesgo que permite cambiar  o disparar la función de activación hacia la izq. o der. para garantizar un aprendizaje exitoso.
2. Se generán los pesos aleatorios Wi1, Wi2 en el rango [-1,1], Wi1=0.3, Wi2=0.7, Wib=0.5
3. Se realiza la suma ponderada de las entradas por los pesos
suma = ((0X0.3)+(0X0.7)) + (1X0.5)
suma = (0 + 0) + 0.5
suma = 0.5
4. Función de activación:

1 si suma+bias >= 0

0 si suma+bias <= 0

Para nuestro caso obtuvimos una suma de 0.5 (de acuerdo con la condición de la función de aptitud) entonces nuestra salida es 0
5. Salida: Obtuvimos una salida 0 y nuestra salida esperada es 0 esta condición se cumple, entonces pasariamos con los valores de las siguientes entradas

#### Caso 2: Entrada 0, Entrada 1 ----> 0
1. Se toman 2 entradas Entrada 0, Entrada 1, el tercer parámetro denominado bias es un valor de sesgo que permite cambiar  o disparar la función de activación hacia la izq. o der,. para garantizar un aprendizaje exitoso.
2. Se generán nuevos pesos aleatorios Wi1, Wi2 en el rango [-1,1], Wi1=0.5, Wi2=0.1, Wib=0.9
3. Se realiza la suma ponderada de las entradas por los pesos
suma = ((0X0.5)+(1X0.1)) + (1X0.9)
suma = (0 + 0.1) + 0.9
suma = 1
4. Función de activación:

1 si suma+bias >= 0

0 si suma+bias <= 0

Para nuestro caso obtuvimos una suma de 1 (de acuerdo con la condición de la función de aptitud) entonces nuestra salida es 1
5. Salida: Obtuvimos una salida 1 y nuestra salida esperada es 0 esta condición no se cumple, entonces regresamos al paso 2 y repetimos el proceso

#### Regresamos al paso 2
2. Se generán nuevos pesos aleatorios Wi1, Wi2 en el rango [-1,1], Wi1=0.1, Wi2=0.1, Wib=0.5
3. Se realiza la suma ponderada de las entradas por los pesos
suma = ((0X0.1)+(1X0.1)) + (1X0.5)
suma = (0 + 0.1) + 0.5
suma = 0.6
4. Función de activación:

1 si suma+bias >= 0

0 si suma+bias <= 0

Para nuestro caso obtuvimos una suma de 0.6 (de acuerdo con la condición de la función de aptitud) entonces nuestra salida es 0
5. Salida: Obtuvimos una salida 0 y nuestra salida esperada es 0 esta condición se cumple, entonces pasariamos con los valores de las siguientes entradas

Este proceso seria el mismo para los dos casos restantes, para fines prácticos resuleve los casos restantes, realizando el proceso antes visto.
#### Caso 3: Entrada 1, Entrada 0 ----> 0
#### Caso 3: Entrada 1, Entrada 1 ---->

| Entrada A| Entrada B | Salida Esperada | Salida Generada |
| ---------|-----------| --------------- | ---------------:|
|   0      |    0      |   0             |0                |
|   0      |    1      |   0             |0                |
|   1      |    0      |   0             |¿?               |
|   1      |    1      |   1             |¿?               |




### Dudas, Comentarios, Críticas constructivas
Twitter: @ugarciacal

# Referencias
- Orallo, J. H., Ferri, C. R., & Quintana, M. J. R. (2004). Introducción a la Minería de Datos.
- Mcculloch, W. S., & Pitts, W. (1990). A LOGICAL CALCULUS OF THE IDEAS IMMANENT IN NERVOUS ACTIVITY. 17.
- Soberanis, M. C. (2018, febrero 13). Inspiración biológica de las redes neuronales artificiales. Recuperado el 5 de mayo de 2019, de Medium website: https://medium.com/soldai/inspiraci%C3%B3n-biol%C3%B3gica-de-las-redes-neuronales-artificiales-9af7d7b906a
- Rosenblatt, F. (1958). The Perceptron: A Probabilistic Model for Information Storage and Organization. 65. Recuperado de http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.335.3398&rep=rep1&type=pdf
