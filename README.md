***

# Maestría en Inteligencia Artificial — Análisis de Ventaja de Género en Educación

![Python](https://img.shields.io/badge/python-3.10%2B-blue.svg)
![Scikit-Learn](https://img.shields.io/badge/scikit--learn-latest-orange.svg)
![Estado](https://img.shields.io/badge/status-completado-success.svg)

Este repositorio contiene el análisis comparativo y la implementación de modelos de aprendizaje supervisado para predecir la **Ventaja de Género Educativa** a nivel mundial, utilizando datos de la UNESCO. El proyecto se enfoca en la selección de modelos robustos para el diagnóstico de políticas educativas.

---

## 👤 Equipo de Trabajo
- **Harold Rodrigo Angulo Arellano**
- **Melissa Figallo Sánchez**
- **Jorge Javier Maldonado Mahauad**
- **Paula Elizabeth Noboa Ramírez**

---

## 📋 Tabla de Contenidos
1. [Descripción del Problema](#-dataset)
2. [Metodología](#-dataset)
3. [Modelos Implementados](#-dataset)
4. [Resultados Clave](#-dataset)
5. [Dataset](#-dataset)
6. [Licencia](#-dataset)
---

## 🚀 Descripción del Problema
El desafío consiste en clasificar la ventaja de género en educación (si un país favorece a mujeres o hombres en matriculación) mediante indicadores globales. El objetivo es identificar patrones socio-educativos mediante algoritmos de clasificación, evitando el sesgo de *data leakage* al utilizar estadísticos históricos agregados en lugar de variables deterministas.

---

## ⚙️ Metodología
El flujo de trabajo sigue las mejores prácticas de Ciencia de Datos:
1. **Análisis Exploratorio (EDA):** Limpieza y tratamiento de datos faltantes (UNESCO UIS).
2. **Preprocesamiento:** Transformación de formato largo a ancho (pivotado por País-Año).
3. **Ingeniería de Características:** Creación de variables de contexto histórico para evitar fugas de datos.
4. **Modelado:** Entrenamiento de 8 modelos de clasificación supervisada.
5. **Evaluación:** Comparación mediante métricas de AUC-ROC, F1-Score y precisión.

---

## 🤖 Modelos Implementados
Comparamos el rendimiento de los siguientes algoritmos:
* **Decision Tree**
* **SVM (Linear & SVC)**
* **Random Forest** (Modelo recomendado)
* **Regresión Logística**
* **KNN**
* **Naive Bayes**
* **XGBoost**

---

## 📊 Resultados Clave
El modelo **Random Forest** demostró ser el más eficaz para la implementación.
* **AUC-ROC:** ~0.86
* **Interpretabilidad:** Alta, gracias a la importancia de las *features* integradas.
* **Robustez:** Excelente manejo de *outliers* y distribuciones no normales presentes en los indicadores globales.

> *Nota: Se recomienda utilizar el cuaderno `Grupo nro 5.ipynb` para visualizar los gráficos de importancia de variables y las curvas ROC.*

---

## Sobre el dataset datos_educativos.csv

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

---

## ⚖️ Licencia
Este proyecto se distribuye bajo la licencia MIT. 

*Fuente de datos: UNESCO Institute for Statistics (UIS) — último acceso: abril 2023.*

---
