# Proyecto-Final-YPF-DS---Grupo-9

Repositorio para el proyecto final del curso de Data Science + IA de Fundación YPF.

**Integrantes del Grupo 9:**
- Lucas Becerra
- Santiago Rubio
- Nicolás Saavedra

## Objetivos del trabajo
*   Desarrollar un modelo de clasificación en machine learning orientado al mantenimiento predictivo de maquinaria industrial.
*   Realizar un Análisis Exploratorio de Datos (EDA) exhaustivo para comprender la dinámica física del equipo (variables termodinámicas y cinemáticas).
*   Abordar y mitigar el desafío estadístico del desbalanceo extremo de clases, dado que los eventos de falla son anomalías poco frecuentes.
*   Identificar visual y analíticamente las fronteras operativas que separan el funcionamiento normal de los diferentes modos de colapso del sistema (sobrecalentamiento, sobretensión, desgaste, etc.).

## Dataset utilizado
**Predictive Maintenance Dataset (AI4I 2020)** proveniente del UCI Machine Learning Repository. 
Consiste en un conjunto de datos sintéticos de alta fidelidad que modela los parámetros operativos de una fresadora industrial. Cuenta con 10.000 registros e incluye variables físicas continuas (temperatura del aire y del proceso, velocidad de rotación, torque y desgaste de la herramienta), así como indicadores binarios que señalan tanto el fallo general de la máquina (`Machine failure`) como los modos de fallo específicos.

## Entregables

### Primera preentrega (16/9)
*   `data_pipeline.ipynb`: Análisis exploratorio del dataset y preprocesamiento inicial. Este notebook incluye:
    *   Evaluación y cuantificación del desbalanceo de clases.
    *   Filtro y separación dinámica de variables numéricas (físicas) y variables binarias (targets).
    *   Análisis estadístico descriptivo (asimetría y curtosis).
    *   Visualizaciones univariadas y bivariadas (histogramas, boxplots/violines de densidad) condicionadas por el target para evaluar el poder predictivo de cada característica.

### Segunda preentrega (26/10)
*   `data_pipeline.ipynb`: Preparación del dataset para modelado y comparación de modelos de clasificación. Se incorporaron:
    *   Limpieza y normalización de los nombres de las columnas.
    *   Codificación de la variable categórica y estandarización de las variables numéricas.
    *   División estratificada de los datos y tratamiento del desbalance mediante SMOTE.
    *   Entrenamiento y optimización de modelos de regresión logística y XGBoost mediante búsqueda aleatoria de hiperparámetros.
    *   Evaluación con precision, recall, F1-score, ROC-AUC y Average Precision. XGBoost obtuvo el mejor desempeño general.
