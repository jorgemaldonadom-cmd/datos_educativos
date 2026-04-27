# Maestría en Inteligencia Artificial
# Asignatura: Aprendizaje Automático
# Trabajo de la semana 2
## Grupo Nro. 5
- Harold Rodrigo Angulo Arellano
- Melissa Figallo Sánchez
- Jorge Javier Maldonado Mahuad
- Paula Elizabeth Noboa Ramírez

#
## **Clasificación de Matrícula Educativa (Mujeres)**
<div align="justify">
Este proyecto compara 8 modelos clasificadores de aprendizaje supervisado para predecir si una mujer se matricula en educación primaria, basándose en un conjunto de indicadores educativos globales (datos_educativos.csv). Los modelos clasificadores utilizados fueron: Árboles de Decisión, SVM, Random Forest, Regresión Logística, KNN, Naive Bayes, SVC y XGBoost.
</div>

### 📝 Descripción del Problema
<div align="justify">
El desafío consiste en clasificar la probabilidad de matrícula educativa femenina. Se utiliza la tasa de matrícula primaria como referencia: si es superior a la mediana global, se etiqueta como "1" (se matricula), de lo contrario como "0". El objetivo es identificar patrones socio-educativos mediante algoritmos de clasificación.
</div>

### ⚙️ Metodología

El flujo de trabajo aplicado sigue las siguientes etapas:

    1.- Análisis Exploratorio de Datos (EDA):

        Carga y limpieza de datos (filtrado por género y nivel educativo).

        Visualización de distribuciones y relaciones entre variables mediante gráficos de dispersión y correlación.

    2.- Preprocesamiento:

        Pivotado: Transformación del dataset a formato ancho (País-Año).

        Imputación: Manejo de valores faltantes mediante la mediana.

        Codificación: Uso de LabelEncoder para variables categóricas.

        Normalización: Aplicación de StandardScaler para estandarizar las características numéricas, garantizando un desempeño óptimo en modelos como SVM y KNN.

    3.- Modelado:

        Entrenamiento de múltiples clasificadores: Árboles de Decisión, SVM, Random Forest, Regresión Logística, KNN, Naive Bayes y XGBoost.

        División de datos: 80% entrenamiento y 20% prueba.

    4.- Evaluación:

        Métricas clave: Accuracy, Recall y F1-Score para evaluar la precisión y capacidad de generalización del modelo.

#

### 📊 Conclusiones

**Conclusión Técnica**

<div align="justify">
El modelo seleccionado para este trabajo es **XGBoost**, ya que presentó el mejor desempeño general con una **precisión del 89.5% y el F1-score más alto (0.8914)**. Fue el modelo más robusto. Su arquitectura de Gradient Boosting le permite corregir errores de árboles anteriores de forma iterativa, lo que resultó ideal para capturar patrones complejos y no lineales entre las tasas de diferentes niveles educativos. Si no se elije este modelo se puede elegir **Random Forest ya que presentó el segundo mejor desempeño general con una precisión del 88.5% y el segundo mejor F1-score (0.8824)**. Al ser un conjunto de múltiples árboles de decisión, redujo significativamente el riesgo de sobreajuste (overfitting). Es excelente para manejar variables que tienen rangos muy distintos (como tasas vs. miles de estudiantes) sin perder precisión. Finalmente **Decision Tree presenta el tercer mejor modelo precisión del 87.55% y F1-score (0.8721)**. Aunque es más simple, demostró una eficacia sorprendente. Su alta precisión indica que existen reglas de decisión muy claras y directas en los datos (por ejemplo: "Si la tasa de secundaria es > X, entonces la primaria femenina es > Y").

**Hallazgos en el Dataset**

A partir del Análisis Exploratorio de Datos (EDA) y el entrenamiento de los modelos, se identificaron los siguientes tres puntos críticos:

**1.- Dependencia Inter-Nivel (Efecto Cascada):** El hallazgo más fuerte es la alta correlación entre la educación secundaria y la primaria. Los modelos identificaron que la Tasa de Matrícula en Secundaria Baja es el predictor más fiable para la estabilidad de la matrícula primaria femenina. Esto sugiere que los países que logran retener a las niñas en la secundaria tienden a tener sistemas de educación primaria mucho más sólidos y universales.

**2.- Simetría de Género en Políticas Educativas:** Existe una correlación extremadamente alta (superior a 0.90 en muchos casos) entre las tasas de matrícula de hombres y mujeres dentro de una misma región. Esto indica que, a nivel global, las fluctuaciones en la matrícula suelen responder a factores estructurales del país (economía, infraestructura, estabilidad política) que afectan a ambos géneros, más que a políticas aisladas para un solo sexo.

**3.- Variabilidad Crítica en Secundaria Alta:** Mientras que la educación primaria muestra tasas cercanas al 100% en muchas regiones (baja variabilidad), la Secundaria Alta presenta los "boxplots" más dispersos y con más valores atípicos. Este nivel educativo es el verdadero diferenciador entre regiones en desarrollo y regiones desarrolladas, y es donde el modelo encuentra más "ruido" o dificultad para predecir, señalando que es el eslabón más frágil de la cadena educativa global.

Este análisis confirma que para mejorar la matrícula femenina, no basta con enfocarse en la primaria; el éxito está intrínsecamente ligado a la capacidad del sistema para proyectar a las estudiantes hacia niveles secundarios.
</div>

### 🛠️ Tecnologías Utilizadas

    Python

    Pandas / NumPy (Manipulación de datos)

    Scikit-learn (Modelado y métricas)

    Seaborn / Matplotlib (Visualización)

    XGBoost

#

### Sobre el dataset datos_educativos.csv

El dataset datos_educativos.csv, contiene información educativa que incluye tasas de matrícula. Está estructurado con registros para diferentes países, años y tipos de datos educativos, junto con la tasa correspondiente y la fuente de los datos.

Origen: Los datos fueron recolectados del archivo datos_educativos.csv.

Documentación del Dataset de Datos Educativos de la ONU

https://www.kaggle.com/datasets/isabelocastillo/datos-educativos-globales/data

Variables Disponibles: Las variables disponibles en el dataset original son:
- Índice: Un identificador numérico de fila.
- ID: Un identificador numérico.
- País: La variable categórica que representa el país.
- Año: El año del registro de la tasa.
- Tipo de Dato Educativo: La categoría específica de la tasa educativa (ej. Tasa Matrícula Primaria (Mujeres)).
- Tasa: El valor numérico de la tasa educativa.
- Fuente Datos: La fuente de donde se obtuvo el dato educativo.

