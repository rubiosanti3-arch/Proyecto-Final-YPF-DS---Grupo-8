# Proyecto-Final-YPF-DS---Grupo-8

Repositorio para el proyecto final del curso de Data Science + IA de Fundación YPF.

## Requisitos para ejecutar los notebooks
- Python 3 y Jupyter Notebook o JupyterLab.
- Instalar las dependencias de análisis y modelado:

```bash
python -m pip install jupyter numpy pandas matplotlib seaborn scipy scikit-learn imbalanced-learn xgboost shap
```

- Ejecutar los notebooks desde la raíz del repositorio. `eda_pipeline.ipynb` utiliza `Material/Datasets/ai4i2020.csv` y genera `Material/Datasets/ai4i2020_model_ready.csv`, que luego utiliza `ml_pipeline.ipynb`.

**Integrantes del Grupo 8:**
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

### Desarrollo final
En `eda_pipeline.ipynb` se exploran el desbalance y los tipos de falla, las distribuciones y relaciones entre variables, y se generan características derivadas como la diferencia térmica y la potencia mecánica.

En `ml_pipeline.ipynb` se comparan modelos de regresión logística, Random Forest y XGBoost, incluyendo estrategias para tratar el desbalance, ajuste de hiperparámetros y validación cruzada anidada. También se analizan curvas Precision-Recall, umbrales de clasificación, escenarios simulados de costos, ablación de características y desempeño final en el conjunto de prueba.

El análisis no supervisado aplica K-Means para identificar y caracterizar grupos operativos, seleccionar la cantidad de clusters y estudiar sus tasas de falla. La interpretabilidad se aborda con Permutation Importance y SHAP, tanto a nivel global como para predicciones individuales.

