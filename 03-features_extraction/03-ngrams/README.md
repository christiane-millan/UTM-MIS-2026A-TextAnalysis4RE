# Análisis de N-Gramas

Con solo saber que _climate_ es una palabra frecuente no dice mucho acerca de los temas de discusión porque, por ejemplo, _climate change_ y _political change_ tiene diferentes significados. Incluso _change climate_ no es lo mismo que _climate change_. Puede por lo tanto ser de gran ayuda extender el análisis de frecuencia de una solo palabra o una secuencia corta de dos o tres palabras. 

Se busca dos tipos de palabras: compuestas (_compounds_) u colocaciónes (_collocations_). Una _compounds_ es una combinación de dos o más palabras con un significado especial. En inglés, se encuentran _compounds_ en forma cercana como: _earthquake_, _self.confident_ y formas abiertas como _climate change_. Por lo tanto, se debe considerar como una solo unidad semántica. _Collocations_ en contraste, son palabras que son de uso frecuente en conjunto. Frecuentemente, consiste en un adjetivo o verbo y un pronombre, como _red carpet_ o _united nations_.

Implementación de n-gramas

```python
def ngrams(token, n=2, sep=' '):
    return [sep.join(ngram) for ngram in zip(*[tokens[i:] for i in range(n)])]

text = "the visible manifestation of the global climate change"
tokens = tokenize(text)
print("|".join(ngrams(tokens, 2)))
````

Salida

```text
the visible|visible manifestation|manifestation of|of the|the global|global climate|climate change
```

Modificación para manejo de _stopwords_.

```python
def ngrams(tokens, n=2, sep=' ', stopwords=set()):
    return [sep.join(ngram) for ngram in zip(*[tokens[i:] for i in range(n)]) if len([t for t in ngram if t in stopwords])==0]

print("Bigrams:", "|".join(ngrams(tokens, 2, stopwords=stopwords)))
print("Trigrams:", "|".join(ngrams(tokens, 3, stopwords=stopwords)))
```

Salida

```text
Bigrams: visible manifestation|global climate|climate change
Trigrams: global climate change
```

