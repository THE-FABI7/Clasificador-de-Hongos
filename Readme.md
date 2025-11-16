
# Proyecto: Clasificación de Hongos (Mushroom) — 3er Parcial Sistemas Inteligentes II

Resumen
-------
Este repositorio contiene un notebook de análisis y modelado para el Mushroom Dataset (UCI). Se entrena un modelo CART, se extraen reglas explícitas del árbol, se analizan sus métricas (pureza, cobertura, simplicidad) y se valida el comportamiento con validación cruzada y optimización de hiperparámetros.

Archivos
--------
- [3er_parcial_sistemas_inteligentes_2.ipynb](3er_parcial_sistemas_inteligentes_2.ipynb) — Notebook principal con todo el flujo: EDA, preprocesamiento, entrenamiento, visualización, extracción y análisis de reglas, validación cruzada y GridSearch.
- [Readme.md](Readme.md) — Este archivo.

Puntos clave del notebook
-------------------------
- Exploración y limpieza de datos (EDA).
- Codificación de variables categóricas y manejo de valores faltantes.
- División Train/Test y entrenamiento de un modelo baseline: [`dt_baseline`](3er_parcial_sistemas_inteligentes_2.ipynb).
- Visualización del árbol con formato profesional: [`plot_decision_tree`](3er_parcial_sistemas_inteligentes_2.ipynb).
- Extracción de reglas explícitas desde el árbol: [`extract_rules`](3er_parcial_sistemas_inteligentes_2.ipynb).
- Análisis y ranking de reglas por pureza, cobertura, simplicidad y score combinado.
- Validación cruzada K-Fold con múltiples métricas via `cross_validate`.
- Optimización de hiperparámetros con GridSearchCV.

Segundo punto del parcial
-------------------------
Objetivo: implementar, evaluar y seleccionar un subconjunto de reglas interpretable y reproducible.
- Extracción detallada de reglas desde el árbol (antecedentes → consecuente).
- Cálculo de métricas por regla: pureza (precision local), cobertura (support), tamaño / simplicidad (número de condiciones).
- Filtrado y ranking de reglas según umbrales definidos (p. ej. pureza >= 0.95 y cobertura >= 0.01).
- Implementación de un clasificador basado en reglas (rule-based classifier) que aplica reglas por orden de prioridad y resuelve conflictos con fallback al modelo DT o al valor mayoritario.
- Comparación del clasificador por reglas vs dt_baseline en métricas globales: accuracy, precision, recall, f1, matriz de confusión.
- Exportación de las reglas seleccionadas a CSV/JSON para revisión y reproducibilidad.

Tercer punto del parcial
------------------------
Objetivo: análisis de interpretabilidad, robustez y conclusiones para entrega.
- Análisis de estabilidad de las reglas mediante K-Fold: comprobar variación de pureza y cobertura entre folds.
- Experimentos de robustez: evaluación en subconjuntos (por ejemplo, atributos clave) y sensibilidad a ruido en atributos categóricos.
- Documentación de reglas “más importantes” con ejemplos de instancias (casos reales del dataset que cumplen la regla).
- Visualizaciones finales: árbol destacado, heatmaps de cobertura/pureza, gráficas de trade-off pureza vs cobertura.
- Recomendaciones finales y conclusiones: cuándo usar el conjunto de reglas versus el árbol completo, limitaciones y posibles mejoras.
- Entrega: notebook con celdas ejecutables (con resultados fijados o random_state), requirements.txt y archivo con reglas exportadas.

Dependencias
------------
Recomendado usar un entorno virtual. Paquetes principales:
- numpy, pandas, matplotlib, seaborn, scikit-learn, scipy

Instalación rápida
------------------
1. Crear e activar entorno virtual.
2. Instalar paquetes:
   pip install numpy pandas matplotlib seaborn scikit-learn scipy

Ejecución
--------
1. Abrir [3er_parcial_sistemas_inteligentes_2.ipynb](3er_parcial_sistemas_inteligentes_2.ipynb) en Jupyter/Colab.
2. Ejecutar las celdas en orden. El notebook está organizado en secciones (EDA → Preprocesamiento → Entrenamiento → Extracción de reglas → Validación cruzada → Optimización → Segundo y Tercer punto).

Consejos
--------
- Revisar los mappings generados por LabelEncoder antes de usar reglas en producción.
- Si se desea reproducir experimentos longevos (GridSearch), ajustar n_jobs y random_state para reproducibilidad.
- Las funciones importantes para inspección rápida son: [`extract_rules`](3er_parcial_sistemas_inteligentes_2.ipynb), [`plot_decision_tree`](3er_parcial_sistemas_inteligentes_2.ipynb) y el objeto [`dt_baseline`](3er_parcial_sistemas_inteligentes_2.ipynb).

Licencia y autor
----------------
Estudiante: Fabian Guancha  
Código y notebook: trabajo para 3er parcial — Sistemas Inteligentes II
// ...existing code...# Proyecto: Clasificación de Hongos (Mushroom) — 3er Parcial Sistemas Inteligentes II

Resumen
-------
Este repositorio contiene un notebook de análisis y modelado para el Mushroom Dataset (UCI). Se entrena un modelo CART, se extraen reglas explícitas del árbol, se analizan sus métricas (pureza, cobertura, simplicidad) y se valida el comportamiento con validación cruzada y optimización de hiperparámetros.

Archivos
--------
- [3er_parcial_sistemas_inteligentes_2.ipynb](3er_parcial_sistemas_inteligentes_2.ipynb) — Notebook principal con todo el flujo: EDA, preprocesamiento, entrenamiento, visualización, extracción y análisis de reglas, validación cruzada y GridSearch.
- [Readme.md](Readme.md) — Este archivo.

Puntos clave del notebook
-------------------------
- Exploración y limpieza de datos (EDA).
- Codificación de variables categóricas y manejo de valores faltantes.
- División Train/Test y entrenamiento de un modelo baseline: [`dt_baseline`](3er_parcial_sistemas_inteligentes_2.ipynb).
- Visualización del árbol con formato profesional: [`plot_decision_tree`](3er_parcial_sistemas_inteligentes_2.ipynb).
- Extracción de reglas explícitas desde el árbol: [`extract_rules`](3er_parcial_sistemas_inteligentes_2.ipynb).
- Análisis y ranking de reglas por pureza, cobertura, simplicidad y score combinado.
- Validación cruzada K-Fold con múltiples métricas via `cross_validate`.
- Optimización de hiperparámetros con GridSearchCV.

Dependencias
------------
Recomendado usar un entorno virtual. Paquetes principales:
- numpy, pandas, matplotlib, seaborn, scikit-learn, scipy

Instalación rápida
------------------
1. Crear e activar entorno virtual.
2. Instalar paquetes:
   pip install numpy pandas matplotlib seaborn scikit-learn scipy

Ejecución
--------
1. Abrir [3er_parcial_sistemas_inteligentes_2.ipynb](3er_parcial_sistemas_inteligentes_2.ipynb) en Jupyter/Colab.
2. Ejecutar las celdas en orden. El notebook está organizado en secciones (EDA → Preprocesamiento → Entrenamiento → Extracción de reglas → Validación cruzada → Optimización).

Consejos
--------
- Revisar los mappings generados por LabelEncoder antes de usar reglas en producción.
- Si se desea reproducir experimentos longevos (GridSearch), ajustar n_jobs y random_state para reproducibilidad.
- Las funciones importantes para inspección rápida son: [`extract_rules`](3er_parcial_sistemas_inteligentes_2.ipynb), [`plot_decision_tree`](3er_parcial_sistemas_inteligentes_2.ipynb) y el objeto [`dt_baseline`](3er_parcial_sistemas_inteligentes_2.ipynb).

Licencia y autor
----------------
Estudiante: Fabian Guancha  
Código y notebook: trabajo para 3er parcial — Sistemas Inteligentes II

