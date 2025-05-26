# Cuantificacion de Incertidumbre

## Planteamiento del problema a resolver
El problema que plantea resolver este proyecto no es tanto relacionado con la diabetes, este es sólo un ejemplo de muchos que se podrían haber elegido. El planteamiento con el que se realiza este proyecto es mostrar una nueva dinámica de trabajo, una dinámica que es más correcta que la que se utiliza actualmente en el entrenamiento de modelos de inteligencia artificial.

El problema principal es la confusión de las llamadas 'raw scores' como probabilidades reales, es importante dejar de confundir estos valores con probabilidades, porque no lo son y asegurarse de convertirlas en probabilidades REALES, calibrándolas antes de dar resultados y segundo, nuestro modelo siempre va a darnos un resultado por muy poco seguro que esté de la predicción que genera, por eso implementar las técnicas de cuantificación de incertidumbre nos permite que el modelo nos comunique qué tan seguro está de los resultados dados y cuáles podemos descartar porque su confiaza en el resultada no es lo suficientemente alta. ¿Cómo nos comunica esto? Con un rango, es decir, en vez de darnos sólo un resultado, nos aportará un rango. En función de la amplitud de este rango, puede saberse si el modelo está seguro de su predicción o no.

Un ejemplo sencillo e ilustrativo es el siguiente, si alguien me pregunta qué edad tiene su hija y yo le respondo que entre 20 y 25 años, estoy indicando que sé con bastante seguridad cuál es su edad real y es altamente probable que el resultado real esté dentro de este rango, sin embargo, si mi respuesta es entre 10 y 40, indico que no tengo mucha idea del resultado y que es probable que mi respuesta no sea de fiar y si ya digo entre 0 y 100, es porque no tengo ni idea y doy un resultado porque es obligatorio responder a la pregunta.

## Descripción del proyecto
Práctica sobre la aplicación de cuantificación de incertidumbre en modelos de clasificación binaria, para explicar la importancia de no considerar las 'raw scores' como probabilidades reales y hacer el modelo de predicción capaz de indicar cuál es su grado de seguridad/fiabilidad sobre el resultado dado.

El dataset elegido no consta de variables categóricas, sólo se analizan numéricas y se usan los modelos de Random Forest y Regresión Logística.

Se realiza una limpieza de datos (eliminación de valores null o similares y posibles valores anómalos como presión sanguínea == 0)

Elección del los modelos utilizados durante el proyecto (Random forest y logistic regresion), he elegido utilizar estos 2 modelos por ser 2 de los algoritmos más usados en el ML para la predicción binaria. Comparar entre ellos los resultados para elegir el modelo que mejor se ajuste al dataset.

Se estudia la relevancia de las diferentes variables y su correlación entre ellas.

Para la elección del modelo y sus hiperparámetros se hace una primera segmentación de los datos en 3 conjuntos (entrenamiento, validación y test), usando así el conjunto de validación para ver los valores de las métricas del modelo reales, no sesgadas. Luego se evalúan los modelos testados con la parte de test.

Una vez elegido un modelo con los mejores hiperparámetros posibles, se vuelve a segmentar el dataset y entrenar de nuevo el modelo, pero esta vez se utilizará un conjunto para calibrar y calcular el rango de amplitud de las probabilidades en las que entra la predicción del modelo.
