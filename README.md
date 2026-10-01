# Actividad 4 · Optimización controlada de un ensamble

[![Abrir en Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Gsmtz29/actividad-4-ensambles/blob/main/actividad_4_ensambles.ipynb)

Comparación reproducible de Random Forest base, selección de 15 características mediante ANOVA y optimización con GridSearchCV. Dataset: Breast Cancer Wisconsin (Diagnostic), [UCI](https://doi.org/10.24432/C5DW2B), incluido en Scikit-learn.

## Ejecución

Abra el notebook con el botón de Colab y seleccione **Entorno de ejecución → Ejecutar todas**. Se usa CPU, semilla 42 y una partición estratificada 80/20. El notebook carga el dataset sin descargar archivos adicionales y genera los entregables en `resultados/`.

También puede ejecutarse con Jupyter y las dependencias de `requirements.txt`. El cuaderno y los resultados publicados corresponden a una ejecución verificada en Google Colab, sin errores. Las versiones se registran en `resultados/versiones.json`; otras versiones pueden producir pequeñas variaciones numéricas o de tiempos.

Resultado principal: F1 base **0.9630**, reducido **0.9367** y optimizado **0.9367**. Se recomienda el modelo base con el criterio fijado en validación cruzada. La búsqueda tardó aproximadamente **48.45 segundos** en esta ejecución de Colab.

## Contenido

- `actividad_4_ensambles.ipynb`: cuaderno documentado, con salidas, tablas, gráficas y conclusión.
- `resultados/dataset_original_sklearn.csv`: versión original distribuida por Scikit-learn (objetivo 0=maligno, 1=benigno).
- `resultados/dataset_procesado.csv`: datos, objetivo recodificado **maligno=1**, identificador de fila y partición. El identificador y la partición no son predictores.
- `resultados/comparacion.csv`: métricas, características, tiempos y validación cruzada.
- `resultados/busqueda_cv.csv`: evidencia de las 16 configuraciones y los cinco folds.
- Gráficas, predicciones y variables seleccionadas para auditar los resultados.

La selección y el preprocesamiento se ajustan dentro de cada fold. La prueba se reserva hasta finalizar la búsqueda. Se informa el costo total de búsqueda por separado del ajuste final y se incluye incertidumbre bootstrap pareada para la diferencia de F1. La conclusión no presupone que optimizar mejora el modelo.
