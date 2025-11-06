# Naive Bayes

El algoritmo Naive Bayes (NB) es un modelo de aprendizaje supervisado ampliamente utilizado para tareas de clasificación, especialmente en el análisis de texto (como detección de spam, análisis de sentimientos, o categorización de documentos).

Su nombre proviene de:

- Bayes, porque se basa en el Teorema de Bayes.
- Naive (ingenuo), porque asume independencia entre las características (lo cual rara vez es completamente cierto, pero funciona sorprendentemente bien en la práctica).

**Intuición del modelo**

El Teorema de Bayes permite calcular la probabilidad de que una observación pertenezca a una clase C_k, dado un conjunto de características X:

$P(C_k | X) = \frac{P(X | C_k) \, P(C_k)}{P(X)}$

Donde:
- $P(C_k | X)$: probabilidad de la clase dado el ejemplo (lo que queremos predecir).
- $P(X | C_k)$: probabilidad de observar las características dado que pertenecen a la clase.
- $P(C_k)$: probabilidad previa de la clase.
- $P(X)$: probabilidad total de los datos (constante para todas las clases).

La suposición naive (ingenua) es que todas las características son independientes entre sí:

$P(X | C_k) = P(x_1 | C_k) \cdot P(x_2 | C_k) \cdot \dots \cdot P(x_n | C_k)$

### MultinomialNB: ideal para texto

El clasificador MultinomialNB es el más usado en NLP y machine learning clásico para texto.
Funciona bien con características que representan frecuencias o conteos, como:
- Bag of Words
- TF-IDF

Fórmula del modelo:

$P(C_k | x) \propto P(C_k) \prod_{i=1}^{n} P(x_i | C_k)^{x_i}$

donde $x_i$ es el conteo o peso de la palabra $i$ en el documento.

**Ventajas y limitaciones**

Ventajas

- Muy rápido y eficiente incluso con muchos datos.
- Ideal para texto (TF-IDF, bag-of-words).
- Funciona bien incluso con pequeñas cantidades de datos.
- Fácil de interpretar.

Limitaciones

- Supone independencia entre características, lo que puede ser irreal.
- No maneja bien datos con valores negativos (por eso no se usa con datos estandarizados).
- No captura relaciones complejas entre variables.

[Ejemplo NB con BoW](./code/classify_naivebayes_i.ipynb)
[Ejemplo NB con reducción de características (steamming) y n-grams](./code/classify_naivebayes_ii.ipynb)
[Ejemplo NB con corrección de data leakage](./code/classify_naivebayes_iii.ipynb)
