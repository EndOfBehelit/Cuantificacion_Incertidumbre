# Cuantificacion_Incertidumbre
Práctica sobre la aplicación de cuantificación de incertidumbre en modelos de clasificación binaria, para explicar la importancia de no considerar las 'raw scores'
 como probabilidades reales y hacer el modelo de predicción capaz de indicar cuál es su grado de seguridad/fiabilidad sobre el resultado dado.

El dataset elegido no consta de variables categóricas, sólo se analizan numéricas y se usan los modelos de Random Forest y Regresión Logística.

Se realiza una limpieza de datos (eliminación de valores null o similares y posibles valores anómalos como presión sanguínea == 0)

Se estudia la relevancia de las diferentes variables y su correlación entre ellas.

Para la elección del modelo y sus hiperparámetros se hace una primera segmentación de los datos en 3 conjuntos (entrenamiento, validación y test),
 usando así el conjunto de validación para encontrar los mejores hiperparámetros posibles para el modelo entrenado.
Luego se evalúan los modelos testeados observando sus diferentes métricas (recall, accuarcy, f1...)

Una vez elegido un modelo con los mejores hiperparámetros posibles, se vuelve a segmentar el dataset y entrenar de nuevo el modelo, pero esta vez se utilizará un conjunto
para calibrar y calcular el rango de amplitud de las probabilidades en las que entra la predicción del modelo.
