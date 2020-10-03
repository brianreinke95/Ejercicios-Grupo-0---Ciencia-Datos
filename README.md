# Ejercicios-Grupo-0---Ciencia-Datos
Grupo 0. 

Integrantes: Tomás De Stefano; Pedro Kopyto; Brian Reinke

## En este repositorio se irán subiendo los distintos ejercicios desarrollados en la cursada.

### Ejercicios de Regresión:

## Support Vector Regression:

Descripción general de SVR

El problema de regresión es una generalización del problema de clasificación, en el que el modelo devuelve una salida de valor continuo, en oposición a una salida de un conjunto finito. En otras palabras, un modelo de regresión estima una función multivariante de valor continuo.

Las SVM resuelven problemas de clasificación binaria formulándolos como problemas de optimización convexa (Vapnik 1998). El problema de la optimización pasa por encontrar el margen máximo que separa el hiperplano, clasificando correctamente tantos puntos de entrenamiento como sea posible. Las SVM representan este hiperplano óptimo con vectores de soporte. 

La escasa solución y la buena generalización de la SVM se prestan a la adaptación a los problemas de regresión. La generalización de SVM a SVR se logra mediante la introducción de una región ε- insensible alrededor de la función, llamada ε-tubo. Este tubo reformula el problema de optimización para encontrar el tubo que mejor se aproxima a la función de valor continuo, mientras equilibra la complejidad del modelo y el error de predicción. 

![image](https://user-images.githubusercontent.com/28718644/94986334-6839f880-0534-11eb-8ff1-a733679b9d2e.png)

Más específicamente, la RVS se formula como un problema de optimización definiendo primero un ε convexo-Función de pérdida insensible para minimizar y encontrar el tubo más plano que contiene la mayoría de las instancias de entrenamiento. 

Por tanto, se construye una función multiobjetivo a partir de la función de pérdida y las propiedades geométricas del tubo. Luego, se resuelve la optimización convexa, que tiene una solución única, utilizando los algoritmos de optimización numérica apropiados. El hiperplano se representa en términos de vectores de soporte, que son muestras de entrenamiento que se encuentran fuera del límite del tubo. 

![image](https://user-images.githubusercontent.com/28718644/94986362-94ee1000-0534-11eb-87ee-dbf822cf61b0.png)

Como en SVM, los vectores de soporte en SVR son las instancias más influyentes que afectan la forma del tubo, y se asume que los datos de entrenamiento y prueba son independientes e idénticamente distribuidos (iid), extraídos de la misma función de distribución de probabilidad fija pero desconocida en un contexto de aprendizaje supervisado.


## K-Neighbors Regression:

K vecinos más cercanos es un algoritmo simple que almacena todos los casos disponibles y predice el objetivo numérico basándose en una medida de similitud (por ejemplo, funciones de distancia). KNN ya se ha utilizado en la estimación estadística y el reconocimiento de patrones a principios de la década de 1970 como una técnica no paramétrica. 		
Una implementación simple de la regresión KNN es calcular el promedio del objetivo numérico de los K vecinos más cercanos. Otro enfoque utiliza un promedio ponderado de la distancia inversa de los K vecinos más cercanos. La regresión KNN utiliza las mismas funciones de distancia que la clasificación KNN.		

![image](https://user-images.githubusercontent.com/28718644/94986306-08435200-0534-11eb-85d9-c6e6ed36863d.png)

Las tres medidas de distancia anteriores solo son válidas para variables continuas. En el caso de variables categóricas, debe usar la distancia de Hamming, que es una medida del número de instancias en las que los símbolos correspondientes son diferentes en dos cadenas de igual longitud. 		


Podemos usar el mismo tipo de enfoque de vecinos más cercanos para las regresiones, donde queremos un valor individual en lugar de una clasificación.

Nuestra 'regresión' en este caso no será una fórmula única como nos daría un modelo OLS, sino más bien un valor de salida mejor predicho para cualquier entrada dada

Sin resolver ninguna ecuación, podemos llegar a una aproximación razonable de cuál debería ser la salida simplemente considerando los puntos cercanos.
Tiene sentido que el valor pronosticado esté cerca de estos puntos, ni mucho más bajo ni más alto. Quizás una buena predicción sería el promedio de estos puntos

![image](https://user-images.githubusercontent.com/28718644/94986589-5a857280-0536-11eb-9b93-2fe2b02708d2.png)

Conectar todas estas predicciones con una línea nos da nuestra regresión:

![image](https://user-images.githubusercontent.com/28718644/94986602-6e30d900-0536-11eb-9a9c-ad2003714b03.png)

una ventaja de la simplicidad de esta implementación es que maneja bien la no linealidad.

![image](https://user-images.githubusercontent.com/28718644/94986451-560c8a00-0535-11eb-919c-716b120198be.png)


La mejor forma de elegir el valor óptimo de K es inspeccionando primero los datos. En general, un valor de K grande es más preciso ya que reduce el ruido general; sin embargo, el compromiso es que los límites distintos dentro del espacio de características se difuminan. 

La validación cruzada es otra forma de determinar retrospectivamente un buen valor de K mediante el uso de un conjunto de datos independientes para validar su valor de K. La K óptima para la mayoría de los conjuntos de datos es 10 o más. Eso produce resultados mucho mejores que 1-NN.







