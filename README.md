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

Este proyecto compara 8 modelos clasificadores de aprendizaje supervisado para predecir si una mujer se matricula en educación primaria, basándose en un conjunto de indicadores educativos globales (datos_educativos.csv). Los modelos clasificadores utilizados fueron: Árboles de Decisión, SVM, Random Forest, Regresión Logística, KNN, Naive Bayes, SVC y XGBoost.

### 📝 Descripción del Problema

El desafío consiste en clasificar la probabilidad de matrícula educativa femenina. Se utiliza la tasa de matrícula primaria como referencia: si es superior a la mediana global, se etiqueta como "1" (se matricula), de lo contrario como "0". El objetivo es identificar patrones socio-educativos mediante algoritmos de clasificación.

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

### 📊 Conclusiones

    Desempeño: Los modelos de ensamble como XGBoost (Accuracy: 89.5%, F1-Score: 89.1%) y Random Forest (Accuracy: 88.9%, F1-Score: 88.2%) mostraron el mejor desempeño en la tarea de clasificación.

    Importancia del Enfoque: El uso de la mediana para definir la variable objetivo permitió trabajar con un dataset balanceado, lo cual es fundamental para que las métricas de Recall y F1-Score sean fiables y no estén sesgadas hacia una clase mayoritaria.

    Insight Educativo: El análisis confirma que la estabilidad del sistema educativo es el predictor más fuerte. La variabilidad observada en niveles de secundaria sugiere que la retención en secundaria alta es el eslabón crítico para cerrar la brecha de género en la matrícula educativa.

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

