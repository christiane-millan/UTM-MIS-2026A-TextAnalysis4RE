# Ingeniería de características

Una de las diferencias principales entre datos textuales y datos estructurados es que el texto esta representado por palabras, mientras que lo más común en datos estructurados son números. 

Para implementar algoritmos de aprendizaje automático es necesario mapear el texto a números. La mayoría de la representación de textos en análisis y aprendizaje automático se basa en vectores. 

Los vectores viven es espacios vectoriales, por lo tanto existen propiedades adicionales como normas y distancias, lo cual puede resultar util (implica el concepto de similitud).

La vectorización de documentos es la base para tareas de aprendizaje automático. Entre los enfoques básicos populares esta la bolsa de palabras (BoW, bag of words), y la mejora TF-IDF.

## Vectorización One-hot

La vectorización _One-hot Encoding_ crea vectores binarios de documentos a partir de la condición si la palabra aparece o no en un documento, resultando en 0 o 1, respectivamente. 

Para crear el vector _one-hot_ es necesario primero crear un vocabulario y asignar números a cada palabra. Después se realiza la vectorización. 

### Enumerar el vocabulario

```python
sentences = ["It was the best of times",
"it was the worst of times",
"it was the age of wisdom",
"it was the age of foolishness"]

tokenized_sentences = [[t for t in sentence.split()] for sentence in sentences]
vocabulary = set([w for s in tokenized_sentences for w in s])

import pandas as pd
pd.DataFrame([[w, i] for i,w in enumerate(vocabulary)])
```

### Vectorizar un documento

Es necesario utilizar el mismo diccionario para vectorizar todos los documentos, con la finalidad de que todos los documentos tengan la misma dimensión. Si el documento no contiene una palabra se coloca un 0, en la posición correspondiente de la palabra, de otro modo, se coloca un 1. Es necesario considerar que el tamaño del vector será tan grande como la longitud del diccionario.

```python
def onehot_encode(tokenized_sentence):
    return [1 if w in tokenized_sentence else 0 for w in vocabulary]

onehot = [onehot_encode(tokenized_sentence) for tokenized_sentence in tokenized_sentences]

for (sentence, oh) in zip(sentences, onehot):
    print("%s: %s" % (oh, sentence))  
```

Salida

```python
[0, 1, 0, 0, 1, 1, 1, 1, 0, 0, 1]: It was the best of times
[1, 0, 0, 0, 0, 1, 1, 1, 1, 0, 1]: it was the worst of times
[0, 0, 1, 0, 0, 1, 1, 0, 1, 1, 1]: it was the age of wisdom
[0, 0, 1, 1, 0, 1, 1, 0, 1, 0, 1]: it was the age of foolishness
```

### Documentos con palabras fuera del vocabulario

En el caso que se agregue un nuevo documento, puede ocurrir que todas las palabras que lo componen estén en el diccionario

```python
onehot_encode("the age of wisdom is the best of times")
```

Salida

```python
[0, 1, 1, 0, 0, 1, 1, 1, 0, 1, 0]
```

Sin embargo, puede ocurrir que ninguna de las palabras se encuentren en el diccionario actual, obteniendo un vector nulo:

```python
onehot_encode("John likes to watch movies. Mary likes movies too.".split())
```

Salida

```python
[0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0]
```

En un sentido estricto esta documento no es similar a ninguna de los otros documentos del corpus, por lo que no podrá interactuar con otros documentos. Esto no es problema para un solo documento, pero si resulta frecuenta, el vocabulario o el corpus necesita ser ajustado.

[Ejercicio One-hot Encoding](./code/onehot.ipynb)
