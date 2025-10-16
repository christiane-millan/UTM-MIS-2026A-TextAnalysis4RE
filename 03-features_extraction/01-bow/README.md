## Análisis de frecuencia de palabras

El análisis de frecuencia de palabras consiste en contar cuántas veces aparece cada palabra en un texto o conjunto de documentos. Esto permite identificar patrones, temas recurrentes y términos clave.

Ejemplos de aplicaciones:

* Detectar las palabras más comunes en reseñas de productos.
* Identificar temas dominantes en un artículo científico.
* Analizar discursos políticos para ver las ideas más repetidas.

En Python podemos utilizar la clase `Counter` de la biblioteca `collections` que cuenta elementos de una lista, en este caso, cadenas que representan tokens o palabras. El resultado de counter es un objeto de tipo diccionario que contiene los elementos como claves y las frecuencias como valores.

````Python
from collections import Counter

tokens = tokenize("She likes my cats and my cats like my sofa.")

counter = Counter(tokens)
print(counter)
````

Salida

```text
Counter({'my': 3, 'cats': 2, 'She': 1, 'likes': 1, 'and': 1, 'like': 1, 'sofa': 1})
```

Mediante el método `update()` de `Counter` se puede ir actualizando con lista de tokens de un segundo documento.

```python
more_tokens = tokenize("She likes dogs and cats.") 
counter.update(more_tokens)
print(counter)
```

Salida:

```text
Counter({'my': 3, 'cats': 3, 'She': 2, 'likes': 2, 'and': 2, 'like': 1, 'sofa': 1, 'dogs': 1})
```

[Ejemplo. Análisis de frecuencia de palabras](./code/word_count.ipynb)
