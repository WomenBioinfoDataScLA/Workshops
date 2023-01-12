# Estadística Básica
> Material creado por la Dra. Ana Julia Velez Rueda
>
>
> **LICENSE**: This work is licensed under a
[Creative Commons Attribution-ShareAlike 4.0 International License][cc-by-sa].
>
>[![CC BY-SA 4.0][cc-by-sa-image]][cc-by-sa]

[cc-by-sa]: http://creativecommons.org/licenses/by-sa/4.0/
[cc-by-sa-image]: https://licensebuttons.net/l/by-sa/4.0/88x31.png
[cc-by-sa-shield]: https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg

### Indice
  #### 1.[¿Qué es la estadística?](#intro)
  #### 2.[Muestra vs Población](#muestra)
  #### 3.[Distribuciones](#distribuciones)
  #### 4.[La normalidad no existe](#normalidad)


### 1.[¿Qué es la estadística?](#indice)

El ser humano al igual que [otras especies](https://pubmed.ncbi.nlm.nih.gov/35695157/) es capaz de reconocer [patrones](https://pubmed.ncbi.nlm.nih.gov/7488849/) y obtener información del mundo que lo rodea. La interpretación de aquellas observaciones no siempre ha sido la más cercana a la realidad, pero nos hemos encargado de ajustar nuestras observaciones, análisis e interpretaciones para lograr una mejor previsibilidad en los eventos que ocurren a nuestro alrededor. Es allí que la estídstica nos brinda la metodología adecuada para recolectar, analizar, interpretar y sacar conclusiones de la información que recolectamos de los distintos eventos observados.

Además nos proporciona métodos para entre otras cosas:

1. Diseño: Planificación y realización de estudios de investigación.
2. Descripción: Resumir y explorar datos.
3. Inferencia: hacer predicciones y generalizar sobre los fenómenos representados por los datos.




### 2.[Muestra vs Población](#muestra)

Ahora bien, cuando se recopilan datos para hacer observaciones sobre el mundo, por lo general no es posible recopilar **TODOS** los datos disponibles...  Por ejemplo, si quisieramos saber cuál es la altura más frecuente de un ser Humano a las distintas edades, quizás pueda resultar un poco tedioso medir la altura de todos los individuos que habitan el planeta tierra. Entonces, en lugar de preguntar a cada persona del mundo cuál es su altura y edad, puede que nos resulte más conveniente tomar una `muestra` de la `población` mundíal y luego usarla para hacer inferencias el comportamiento de la `población`.

`Población` y `muestra` son dos conceptos básicos de la estadística. La **`población`** se puede definir como el conjunto de personas, el universo de observaciones posibles u objetos en los se enfoca una investigación. Mientras que, **`muestra`** se denomina al **subconjunto** de individuos, objetos o eventos efectivamente estudiados de esa población. 


### 3.[Distribuciones](#distribuciones)

Resulta que podemos aprender mucho sobre cómo ocurre algo, incluso si no conocemos el proceso subyacente que lo causa. Por ejemplo, observar qué valores son comunes (frecuentes) y cuáles poco comunes, y hacer predicciones sobre los valores que tomará tal o cual variable (característica), aún cuando no sepamos por qué. 

Es decir que un fenómeno observado a través de sus datos, podría ser expresado en función no solo de los posibles valores que puede tomar cada variable, si no también de la frecuencia con que estas toman dichos valores. A la función matemática que describe los posibles valores para una variable y la frecuencia con que estos ocurren se la conoce como **`dístribución`**.

📊 Se suele representar gráficamente la distribución las variables que caracterizan a una muestra con un gráico que describe la probabilidad de ocurrencia de cada evento (frecuencia). Pero es importante comprender que la distribución está definida por las probabilidades subyacentes y no por el gráfico en sí. El gráfico es solo una representación visual que nos facilitará el análisis.

<img src="distributions.png" alt="distributions" style="width: 350px">

Hay muchos tipos distintos de distribuciones estadísticas.  Conocer las características de estas distribuciones, nos permitirá caracterizar aquel conjunto de datos que se comporten de manera similar, además de comparar conjuntos de datos de interés. En general las características de una muestra puede resumirse mediante parámetros numéricos que pueden ser inferidos gracias a la estadística. Algunos de estos parámetros seguramente te resulten conocidos, como la `media` (o promedio) o la `mediana`, y los revisaremos más en detalle cuando sea necesario. Pero es importante comprender que son estos parámetros los que nos ayudarán a caracterizar nuestras datos y compararlos con otro conjunto de datos.


### 4.[La normalidad no existe](#normalidad)

En ciencia nos resulta de gran utilidad contar con sistemas de referencia, de los que tenemos absoluto conocimiento de su funcionamiento para poder contrastar con aquellos completamente nuevo y desconocido. Y esto se relaciona con la forma en la que conocemos y aprendemos los seres humanos... según algunos teóricxs, que plantean que no podemos conocer aquello para de lo que no tenemos una idea previa, porque no tenemos una estructura previa con la cuál establecer relaciones. Algo así como la razón por la que pensamos la vida extraterrestre como seres antropomórficos con cabezas y cerebros grandes 👽, porque sabemos que existe una relación entre el tamaño del cerebro y la inteligencia... y porque creemos que los seres Humanos somos los mejores 😜 

Y así como buscamos vidas similares a las que conocemos en otros rincones del universo, también recurrimos a distribuciones teóricas, con parámetros predecibles o esperables, para comparar y comprender como se comportan conjunto de datos desconocidos. La distribución normal es una distribución teórica por demás utilizada en estadística. ¿Qé quiere decir que sea un distribución teórica? simplemente que su distribución de frecuencias deriva de una fórmula en lugar de provenir de observaciones reales.

La asunción de la normalidad es importante para muchas pruebas estadísticas. Si la forma de la distribución de una muestra no tiene la forma típica de campana de la distribución normal, es posible que algunas pruebas estadísticas no sean válidas para anlizar ese conjunto de datos. Pero a pesar de que la distribución normal es teórica, las distribuciones de muchos datos provenientes del mundo real se parecen a la distribución normal. Y es por ello que conocer las características de la misma, nos servirá para inferir si nuestros datos se comportan o no de forma "normal".

La distribución normal es el un tipo de distribución con simetría central, esto quiere decir que la frecuencia de los datos aumenta hacia un valor en medio del gráfico:

<img src="dist_normal.png" alt="distribucion_normal" style="width: 350px">

Ese valor central se conoce como `media` o promedio aritmético de los valores (es decir la suma de los valores dividido el número total de valores). Este parámetro es una medida de centralidad. En una districbución normal la `media` coincide con otros parámetros: la `mediana` (el valor por encima y por debajo del cual se encuentran la mitad de los eventos) y la `moda` (el de mayor frecuencia)... Es decir que en una distribución normal, el valor más frecuente es justamente el valor promedio. 

Ahora bien, el valor más frecuente no es el único posible no. Una variable podría tomar a priori infinitos valores... ¿cuántos? ¿Muy distintos del más común o frecuente? Bueno, para responder esta pregunta podemos ver cuánto se dispersan los valores respecto del eje central (`media`), es decir ver cuán lejos llegan... Esta medida se conoce como `varianza`. 

Ahora que conocemos un poco más sobre distribuciones y estadística, ya podemos comenzar con los contenidos específicos de **Análisis Datos**

<details>
  <summary>  **Para pensar más allá de la estadística** 🤔 </summary>

Es común escuchar **"la ciencia afirma qué"**, pero no resulta tan común escuchar explicaciones sobre cómo afirma la ciencia. 
¿Qué hace a un conocimiento `científico`? ¿Alguna vez te pusiste a pensar cómo conocemos y qué es el conocimiento? La filosofía de la ciencia se enfoca particularmente en esta pregunta. 

Aquí te dejamos algunos videos para comenzar a pensar juntxs los alcances e implicancias de cómo conocemos y cómo es que afirmamos en ciencia.. de datos 😜 

 - [El conocimiento - Mentira la Verdad](https://www.youtube.com/watch?v=v-Z9eMt-8UU&t=581s)
 - [Los patovicas de la ciencia](https://www.youtube.com/watch?v=ZMUjO5N9BCo) 

</details>
