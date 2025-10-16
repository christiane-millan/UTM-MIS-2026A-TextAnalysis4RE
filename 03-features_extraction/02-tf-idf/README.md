## Ranking con TF-IDF

### Frecuencia Inversa de Documento

La Frecuencia Inversa de Documento (IDF) es un factor de pesado que mide lo inusual de un término en el corpus. Es utilizado frecuentemente para reducir la influencia de términos comunes para el **análisis de datos** o del aprendizaje automático. 

Para explicarlo, se define _document frecuency_ ($df$) de un termino $t$. Dado un corpus (conjunto de documentos) $C$. El $df(t)$ es simplemente el número de documentos $d$ en $C$ que contienen el término $t$. 

$df(t) = |\{d \in C | t \in d\}|$

Los términos que aparecen en muchos documentos tienen un alto $df$. A partir de esta concepto se puede definir el _inverse document frequency idf(t)_ como:

$idf(t) = \log \big( \frac{|C|}{df(t)} \big)$

El logaritmo es utilizado para la escala sublineal. De otro modo, palabras raras podrían tomar valores IDF extremadamente altos. Nótese que $idf(t)=0$ para términos que aparecen en todos los documentos, es decir, $df(t) = |C|$. Para no ignorar completamente estos términos, algunas librerías agregan una constante al termino completo. Se agregar el termino 0.1, el cual es aproximadamente el valor de los tokens que aparecen en el 90% de los documentos $(\log(1/0.9))$.

Para el pesado de un término $t$ en un conjunto de documentos $D \subset C$, se calcula el puntaje TF-IDF como el producto de $tf(t,D)$ y el IDF del término $t$:

$tfidf(t, D) = tf(t, D) \cdot idf(t)$

Esta puntuación produce altos valores para términos que aparecen frecuentemente en los documentos seleccionados $D$ pero raramente en otros documentos del corpus.

