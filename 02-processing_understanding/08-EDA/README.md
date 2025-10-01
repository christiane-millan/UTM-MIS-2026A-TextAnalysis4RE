# Análisis de texto

El análisis de textos involucra un análisis sistemático de los patrones de uso de las palabras en los textos, y por lo general, se combinan métodos estadísticos formales y técnicas interpretativas menos formales y más humanistas.

En cuando al análisis de texto, el análisis de la frecuencia de de palabras o frases es una de los métodos principales de exploración de los datos. La frecuencia de palabras no es en sí interesante, pero la frecuencia relativa o pesada, so lo es. Si se compara la frecuencia relativa de las palabras en un texto, se pueden obtener insgiths sobre la diferencia entre distintos textos, aunque sean del mismo tema. 

Antes de comenzar un análisis de un texto, es necesario comenzar con un Análisis Exploratorio de Datos. El Análisis Exploratorio de Datos (EDA) es el proceso sistemático de examinar datos en un nivel de agregación. Incluye estadística de resumen para características numéricas, conteos de frecuencia para características categóricas. Histogramas y gráficas de caja para ilustrar la distribución de los datos y gráficos de series de tiempo para mostrar su evolución 

[Ejemplo. Análisis estadístico básico](./code/eda_text.ipynb)


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
