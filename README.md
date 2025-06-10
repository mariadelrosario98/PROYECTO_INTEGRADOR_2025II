# PROYECTO_INTEGRADOR_2025II

# Detección y Análisis del Trabajo Infantil en Colombia  
**(Proyecto de Ciencia de Datos con Modelos de Regresión Logística usando la GEIH)**


---

## Contexto y Motivación

El trabajo infantil sigue siendo un fenómeno crítico en países en vías de desarrollo, generando impactos negativos en el capital humano y la movilidad social. En Colombia, recientes datos del DANE y la OIT evidencian que la problemática persiste tanto en áreas rurales como urbanas y afecta principalmente a hogares con condiciones socioeconómicas vulnerables.

Este proyecto busca aportar soluciones preventivas y de bajo costo para la identificación de niños en riesgo, facilitando la priorización de intervenciones sociales y el diseño de políticas públicas focalizadas.

---

## Metodología

### 1. **Exploración y Preparación de Datos**

- Análisis exploratorio de la base GEIH: identificación de variables relevantes, análisis de desbalance y detección de valores nulos o atípicos.
- Imputación de valores faltantes (moda para categóricas, percentil 75 para numéricas).
- Codificación de variables categóricas y estandarización numérica (LabelEncoder, StandardScaler).
- Manejo del desbalance de clases aplicando **SMOTE** para generar instancias sintéticas de la clase minoritaria.

### 2. **Ingeniería de Características**

- Eliminación de variables altamente correlacionadas (>80%) para evitar multicolinealidad.
- Selección de variables predictoras a partir de análisis estadístico y relevancia conceptual.
- Construcción de un pipeline automatizado para todo el preprocesamiento.

### 3. **Modelamiento y Evaluación**

- Entrenamiento y comparación de modelos supervisados:
    - Regresión logística (modelo final elegido por su interpretabilidad y robustez).
    - XGBoost (explorado como benchmark, pero descartado por complejidad y escasa mejora en métricas).
- División de los datos en entrenamiento (70%), validación (15%) y prueba (15%), de forma estratificada.
- Evaluación del desempeño usando precisión, recall y F1-score, priorizando la capacidad de identificar la clase minoritaria.

### 4. **Interpretabilidad y Resultados**

- Análisis de importancia de variables mediante coeficientes y métodos avanzados (SHAP, Permutation Importance).
- Presentación de insights claves sobre los factores de riesgo y recomendaciones de política pública.

---

## Principales Resultados

- El modelo de regresión logística alcanzó una **precisión de 98%**, **recall de 98%** y **F1-score de 99%** en el conjunto de validación.
- Factores como tamaño del hogar, estrato socioeconómico, y permanencia escolar se identificaron como los predictores más importantes.
- La técnica SMOTE fue fundamental para equilibrar los datos y mejorar la capacidad de generalización.
- Se diseñó un pipeline reproducible para la integración y despliegue del modelo en contextos institucionales (como la GEIH).

---

## Despliegue

- **Integración:** El sistema se conecta automáticamente a bases de datos de encuestas periódicas.
- **Predicción:** El modelo calcula la probabilidad de riesgo y clasifica a los niños como "en riesgo" o "no en riesgo".
- **Alertas:** Se generan alertas y reportes para priorizar la atención social en regiones o grupos vulnerables.
- **Monitoreo:** El desempeño del modelo se revisa periódicamente y se actualiza con nuevos datos y retroalimentación de equipos de campo.


