# Tokenización

Los tokens son componentes textuales independientes y mínimos que tienen alguna sintaxis o semántica definida.

La tokenización puede ser definida como el proceso de separa datos textuales en pequeños componentes con significado llamados tokens.

## Tokenización de palabras

La **tokenización de palabras** es el proceso de separar o sementar oraciones en las palabras que la conforman. Una oración es una colección de palabras, y con la tokenización se obtiene una lista de palabras a partir de la oración que pueden ser utilizadas para reconstruir la oración.

```python
from nltk.tokenize import word_tokenize
word_tokenize("Hi there!")
```

```
['Hi', 'there', '!']
```

La tokenización de palabras es importante en muchos procesos, especialmente en la limpieza y normalización de los textos donde operaciones como stemming o lematización se aplica sobre cada palabra basado en sus respectivos stems (raíces) o lemas. 

[Ejemplo 2. Tokenización de palabras](./code/tokenization_words_nltk.ipynb)

## Otros tokenizadores en nltk

### Tokenización de oraciones

La **tokenización de oraciones** es el proceso de separar un corpus de texto en sentencias que actúan como el primer nivel de tokens que componen el corpus.

NLTK (kit de herramientas de lenguaje natural, o más comúnmente NLTK) es un conjunto de bibliotecas y programas para el procesamiento del lenguaje natural (PLN) simbólico y estadísticos para el lenguaje de programación Python.

```python
from nltk.tokenize import sent_tokenize

texto = "La inteligencia artificial avanza rápidamente. Muchos investigadores trabajan en nuevos modelos."

oraciones = sent_tokenize(texto)
print(oraciones)
# Salida: ['La inteligencia artificial avanza rápidamente.', 
#          'Muchos investigadores trabajan en nuevos modelos.']
```

Existen varias formas de realizar la tokenización de sentencias. Las técnicas básicas incluyen buscar delimitares específicos entre sentencias, como el punto y aparte `.` o un carácter de nueva línea `\n`, y algunos otras veces punto y coma `;`.

[Ejemplo 1. Tokenización de oraciones](./code/tokenization_sentences_nltk.ipynb)

### Tokenización mediante expresiones regulares

La función `regexp_tokenize` permite dividir un texto en tokens (palabras, números o símbolos) usando un patrón definido con expresiones regulares.

Esto le da flexibilidad al analista, pues puede decidir qué extraer del texto según la necesidad.

```python
from nltk.tokenize import regexp_tokenize

texto = "La IA en 2025 es increíble, ¿cierto?"

# Extraer solo palabras
tokens_palabras = regexp_tokenize(texto, pattern=r'\w+')
print(tokens_palabras)
# Salida: ['La', 'IA', 'en', '2025', 'es', 'increíble', 'cierto']

# Extraer solo números
tokens_numeros = regexp_tokenize(texto, pattern=r'\d+')
print(tokens_numeros)
# Salida: ['2025']
```

### TweetTokenizer

El TweetTokenizer está diseñado para trabajar con textos de Twitter.
Reconoce elementos que no suelen aparecer en otros tipos de documentos:

- Hashtags (#tema).
- Menciones (@usuario).
- Emojis y emoticonos.
- Contracciones y puntuación informal.

```python
from nltk.tokenize import TweetTokenizer

tweet = "Hola @Juan! Hoy lanzamos el nuevo modelo #IA2025 🚀😃"

tokenizer = TweetTokenizer()
tokens = tokenizer.tokenize(tweet)
print(tokens)
# Salida: ['Hola', '@Juan', '!', 'Hoy', 'lanzamos', 'el', 'nuevo', 'modelo', '#IA2025', '🚀', '😃']
```

### TreebankWordTokenizer

```python
from nltk.tokenize import TreebankWordTokenizer
tokenizer=TreebankWordTokenizer()
tokenizer.tokenize(corpus)
```