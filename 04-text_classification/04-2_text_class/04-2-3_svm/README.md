# Máquina de Soporte Vectorial

Las Máquinas de Soporte Vectorial (Support Vector Machines, SVM) son modelos de aprendizaje supervisado utilizados principalmente para clasificación y, en menor medida, para regresión.

El objetivo de una SVM es encontrar el hiperplano óptimo que separe los datos de distintas clases con el mayor margen posible.

En términos simples, busca una frontera de decisión que maximice la distancia entre los puntos de ambas clases más cercanos a esa frontera, conocidos como vectores de soporte.

**Tipos de SVM**

1.	Lineal (LinearSVC, SVC(kernel='linear')). Para datos linealmente separables.
2.	No lineal (SVC con kernels como rbf, poly, sigmoid). Para datos donde la frontera de decisión es curva o compleja.


[Ejemplo clasificación LinearSVC](./code/classify_svc_i_tfidf.ipynb)

## Balanceo de clases

En muchos problemas de aprendizaje automático, los datos disponibles no están distribuidos de forma equilibrada entre las clases. Por ejemplo, en un conjunto de datos de detección de fraudes bancarios, es común que el 99% de las transacciones sean legítimas y solo el 1% sean fraudulentas.

A este tipo de situación se le conoce como desbalance de clases (class imbalance) y puede causar que los modelos aprendan a favorecer la clase mayoritaria, ignorando la minoritaria. En consecuencia, se obtienen métricas engañosas: el modelo parece tener alta precisión, pero en realidad falla en detectar los casos importantes.

Balancear las clases significa ajustar la proporción de muestras entre las clases del conjunto de datos para que el modelo aprenda de manera más justa y efectiva.

Existen tres estrategias principales:
1.	Submuestreo (undersampling): Se eliminan ejemplos de la clase mayoritaria hasta equilibrar las proporciones.

    - Ventaja: rápido y simple.
	- Desventaja: se pierde información potencialmente útil.

2.	Sobremuestreo (oversampling): Se generan copias o nuevas muestras de la clase minoritaria.
    - Ventaja: se conserva toda la información.
    - Desventaja: puede provocar overfitting.
	
3.	Generación sintética (SMOTE y variantes): Se crean nuevas instancias sintéticas de la clase minoritaria mediante interpolación.

    - Ventaja: más variedad en las muestras.
    - Desventaja: puede generar ruido si las clases se solapan.

### `imbalanced-learn`

**imbalanced-learn (o imblearn)** es una librería de Python diseñada para trabajar junto con scikit-learn. Proporciona herramientas para aplicar técnicas de sobremuestreo, submuestreo y combinaciones de ambas de manera sencilla.

[Ejemplo imbalanced-learn con SVC](./code/classify_svc_ii_tfidf_balance.ipynb)