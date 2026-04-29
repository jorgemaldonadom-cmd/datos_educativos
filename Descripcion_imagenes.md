# Resultados Visuales y Análisis de Modelos

A continuación, se presentan los hallazgos gráficos obtenidos tras el análisis exploratorio y la implementación de los 8 modelos de clasificación para la predicción de la Ventaja de Género Educativa (UNESCO).

## Resumen de Figuras

| Figura | Título | Descripción |
| :--- | :--- | :--- |
| 1 | Ranking de Modelos (F1-Score) | Clasificación jerárquica de los modelos basada en su capacidad predictiva balanceada. |
| 2 | Importancia de Variables | Identificación de los predictores clave (features) en modelos basados en árboles. |
| 3 | Curvas ROC (AUC) | Comparativa de la capacidad de discriminación entre clases de todos los modelos. |
| 4 | Matrices de Confusión | Detalle de aciertos y errores de clasificación para cada algoritmo evaluado. |
| 5 | Comparativa de Métricas | Análisis integral de Accuracy, Precision, Recall y F1-Score por modelo. |
| 6 | Tendencia Temporal VGE | Evolución histórica (2000-2022) de la ventaja de género por nivel educativo. |
| 7 | Correlación y Proporción | Relación entre indicadores y distribución de la paridad por nivel. |
| 8 | QQ-Plots (Normalidad) | Evaluación de la distribución de las tasas de matrícula frente a una normal. |
| 9 | Histogramas y Densidad | Análisis de sesgo y distribución de frecuencias en los datos educativos. |
| 10 | Análisis de Atípicos | Detección de outliers en tasas y brechas mediante diagramas de caja. |

---

## Detalle de las Figuras

### Figura 1 - Ranking de Modelos Finales
* **Descripción:** Gráfico de barras que ordena los modelos según su F1-Score. Resalta el "Podio" de los tres mejores clasificadores.
* **Valor Analítico:** Establece a Random Forest como el modelo líder (F1=0.7337), seguido de XGBoost. Es la base para la selección del modelo de producción.

### Figura 2 - Importancia de las Características
* **Descripción:** Comparativa de los factores que más influyen en la predicción para Decision Tree, Random Forest y XGBoost.
* **Valor Analítico:** Identifica que la 'Brecha_media' es el predictor dominante, validando que el modelo captura la lógica del dominio educativo.

### Figura 3 - Curvas ROC Comparativas
* **Descripción:** Representación de la tasa de verdaderos positivos frente a falsos positivos para los 8 modelos.
* **Valor Analítico:** El AUC permite confirmar la robustez del modelo; cuanto más se acerca la curva al borde superior izquierdo, mejor es la capacidad del modelo para diferenciar las clases sin errores.

### Figura 4 - Matrices de Confusión por Modelo
* **Descripción:** Desglose de predicciones correctas e incorrectas para cada algoritmo evaluado.
* **Valor Analítico:** Permite observar el balance entre Falsos Positivos y Falsos Negativos, crucial para entender el impacto de las decisiones del modelo en el diagnóstico de políticas educativas.

### Figura 5 - Resumen de Métricas de Rendimiento
* **Descripción:** Gráfico de barras agrupadas que consolida Accuracy, Precision, Recall y F1-Score.
* **Valor Analítico:** Facilita la detección de modelos con alto Accuracy pero bajo Recall, asegurando una selección técnica equilibrada y no sesgada por clases mayoritarias.

### Figura 6 - Tendencia Temporal de la Ventaja de Género
* **Descripción:** Líneas de tiempo (2000-2022) que muestran la evolución de la paridad de género por nivel educativo.
* **Valor Analítico:** Contextualiza los datos, mostrando que la brecha no es estática y justificando la inclusión del factor temporal en el entrenamiento del modelo.

### Figura 7 - Correlación de Ventaja y Proporciones
* **Descripción:** Heatmap de correlación y barras de proporción de ventaja femenina/masculina por nivel educativo.
* **Valor Analítico:** Explica la dependencia entre variables socio-educativas y muestra en qué niveles (ej. Secundaria Alta) la ventaja de un género es más prevalente.

### Figura 8 - Diagnóstico de Normalidad (QQ-Plots)
* **Descripción:** Gráficos de probabilidad que comparan la distribución de las tasas contra una normal teórica.
* **Valor Analítico:** Valida estadísticamente que los datos presentan desviaciones de la normalidad, justificando el uso de modelos no paramétricos como árboles y ensambles.

### Figura 9 - Histogramas y Curvas de Densidad (KDE)
* **Descripción:** Distribución de frecuencias y densidad de las tasas de matrícula por género.
* **Valor Analítico:** Revela sesgos de distribución y la concentración de países en rangos específicos de matrícula, detectando desequilibrios globales iniciales.

### Figura 10 - Análisis de Atípicos y Distribución de Brechas
* **Descripción:** Diagramas de caja que identifican valores extremos en las tasas de matrícula y la brecha de género.
* **Valor Analítico:** Crucial para la limpieza de datos; permite visualizar la separación de la brecha entre las clases objetivo (0 y 1) que el modelo debe aprender a clasificar.
