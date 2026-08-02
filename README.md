# Predicción de Lluvia en Australia — Análisis CRISP-DM

Proyecto de la asignatura **BIY7121 – Minería de Datos** (DUOC UC), desarrollado en conjunto por **Bryan Acuña** y **Manuel Rivas**.

## Descripción

El proyecto aplica la metodología **CRISP-DM** sobre un dataset de observaciones meteorológicas diarias de Australia (Commonwealth Bureau of Meteorology), con el objetivo de predecir si lloverá al día siguiente (`RainTomorrow`) y estimar la cantidad de precipitación (`RISK_MM`).

El notebook cubre las 6 fases del proyecto:

1. **Business Understanding** — contexto del negocio y objetivos.
2. **Data Understanding** — exploración de variables, distribución de la variable objetivo, valores nulos, outliers y correlaciones.
3. **Data Preparation** — extracción de componentes de fecha, tratamiento de outliers (capping IQR), imputación de nulos, codificación de variables categóricas (Label/One-Hot Encoding) y escalado (`StandardScaler`).
4. **Modeling** — modelos supervisados (clasificación y regresión) y no supervisados (clustering):
   - Regresión Logística, Random Forest, Gradient Boosting (clasificación).
   - K-Means, Clustering Jerárquico Aglomerativo, Gaussian Mixture Model, DBSCAN (segmentación climática).
5. **Evaluación de Resultados** — comparación de modelos, interpretación de la matriz de confusión, importancia de variables y conclusiones.
6. **Panel de Control (Dashboard)** — dashboard interactivo construido con matplotlib/seaborn que resume accuracy de los modelos, matriz de confusión, variables más importantes y segmentación climática, actualizándose automáticamente al reentrenar los modelos.

## Dataset

- **Fuente:** Observaciones meteorológicas diarias de Australia — Commonwealth Bureau of Meteorology.
- **Archivo:** `weatherAUS.csv` (no incluido en el repositorio, ver sección "Cómo ejecutar").

## Librerías utilizadas

**Análisis y visualización**
- `pandas`, `numpy`
- `matplotlib`, `seaborn`

**Preprocesamiento**
- `scikit-learn` (`preprocessing`: `LabelEncoder`, `StandardScaler`, `MinMaxScaler`)
- `scikit-learn` (`model_selection`: `train_test_split`)
- `scikit-learn` (`impute`: `SimpleImputer`)

**Modelos supervisados**
- `scikit-learn` (`linear_model`: `LinearRegression`, `LogisticRegression`)
- `scikit-learn` (`tree`: `DecisionTreeClassifier`)
- `scikit-learn` (`ensemble`: `RandomForestClassifier`, `GradientBoostingClassifier`)
- `scikit-learn` (`svm`: `SVC`)

**Modelos no supervisados**
- `scikit-learn` (`cluster`: `KMeans`, `DBSCAN`, `AgglomerativeClustering`)
- `scikit-learn` (`decomposition`: `PCA`)
- `scikit-learn` (`mixture`: `GaussianMixture`)

**Métricas**
- `scikit-learn` (`metrics`: `accuracy_score`, `classification_report`, `confusion_matrix`, `mean_squared_error`, `r2_score`, `silhouette_score`)

## Cómo ejecutar

1. Clonar el repositorio.
2. Instalar las dependencias:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn
   ```
3. Descargar el dataset `weatherAUS.csv` y ubicarlo en la raíz del proyecto.
4. Abrir el notebook `BIY7121_EV3_Acuña_Rivas_con_Dashboard.ipynb` y ejecutar las celdas en orden.

## Autores

- Bryan Acuña
- Manuel Rivas
