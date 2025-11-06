# Regresión Logística

La Regresión Logística es uno de los modelos más utilizados en Machine Learning para problemas de clasificación.
Aunque su nombre contiene la palabra regresión, su objetivo principal no es predecir valores continuos, sino clasificar observaciones en categorías (por ejemplo, “spam” o “no spam”, “aprobado” o “reprobado”). Es decir, la regresión logística es un modelo de clasificación que se desempeña muy bien en clases de separación no lineal. Es un modelo de clasificación binario.

La regresión logística modela la probabilidad de que una observación pertenezca a una clase.
Para lograrlo, utiliza la función sigmoide (o logística), que transforma una combinación lineal de variables en un valor entre 0 y 1.

$\sigma(z) = \frac{1}{1 + e^{-z}}$

donde:

$z = w_0 + w_1x_1 + w_2x_2 + \dots + w_nx_n$

El resultado, $\sigma(z)$, puede interpretarse como la probabilidad de pertenecer a la clase $1$.

- [Ejemplo Regresión Logística - BoW](./code/classify_lr_i.ipynb)
- [Ejemplo Regresión Logística - TF-IDF](./code/classify_lr_ii_tfidf.ipynb)


