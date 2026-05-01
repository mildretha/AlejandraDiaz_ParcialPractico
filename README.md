

## Arquitectura Predictiva para la Detección Inteligente de Fraude Financiero

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/6ee90558-87f1-4c62-915a-b73681214d65" />




Esta evaluación un sistema de clasificación para la identificación de transacciones fraudulentas en un entorno de datos altamente desbalanceado. El objetivo es construir modelos capaces de detectar con precisión la clase minoritaria (fraude), minimizando el riesgo de falsos negativos en un contexto donde las pérdidas económicas pueden ser significativas.

### Enfoque metodológico

El trabajo parte de un conjunto de datos donde la proporción de fraude es extremadamente baja, lo que dificulta el aprendizaje de los modelos tradicionales. Para abordar este desafío, se implementa una estrategia de sobremuestreo mediante SVMSMOTE, incrementando la representación de la clase minoritaria hasta un 15% en el conjunto de entrenamiento. Esta decisión permite mejorar la capacidad de los modelos para capturar patrones relevantes sin distorsionar de forma significativa la distribución original de los datos.

El procesamiento y modelado se realizan en PySpark, lo que facilita el manejo de grandes volúmenes de información y la construcción de pipelines escalables.

### Modelos evaluados

Se entrenaron y compararon tres enfoques de clasificación:

- Regresión Logística
<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/b2332b48-2724-4d88-aa28-f0ee167dee43" />


- Regresión Logística con regularización L1 (Lasso)
<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/18ba02ed-a889-4d67-a848-1d7a0c08153a" />

- Random Forest
<img width="1536" height="1024" alt="RF_model" src="https://github.com/user-attachments/assets/f2a995dd-df9a-472e-bd42-5fe68a43131a" />


Cada modelo fue evaluado utilizando métricas robustas para escenarios desbalanceados, incluyendo AUC, PR-AUC, Precision, Recall y F1 Score. Se priorizó especialmente la capacidad de detección de la clase minoritaria.

### Resultados y hallazgos

Los resultados muestran un alto desempeño general en los modelos evaluados; sin embargo, Random Forest destaca por su mejor equilibrio entre precisión y capacidad de detección de fraude. Su arquitectura basada en múltiples árboles permite capturar relaciones no lineales y patrones complejos que los modelos lineales no logran representar completamente.

Asimismo, se reconoce que las métricas obtenidas pueden estar influenciadas por el proceso de balanceo, por lo que se enfatiza la importancia de validar el modelo en datos con distribución real antes de su despliegue en producción.

### Recomendaciones

Se propone el uso de Random Forest como modelo principal para implementación, acompañado de análisis adicionales de importancia de variables y correlaciones. Este paso es fundamental para evitar sesgos, mejorar la interpretabilidad y garantizar la robustez del sistema en escenarios reales.

### Tecnologías utilizadas

- PySpark para procesamiento distribuido
- imbalanced-learn para técnicas de sobremuestreo
- Modelos de clasificación de Spark MLlib
- Python para integración y análisis

### Conclusión

El proyecto demuestra que, en problemas de fraude altamente desbalanceados, la combinación de técnicas de balanceo controlado y modelos capaces de capturar complejidad estructural permite obtener soluciones efectivas y aplicables en el sector financiero.
