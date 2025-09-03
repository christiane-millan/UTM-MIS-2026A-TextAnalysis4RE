# Limpieza de datos

Los datos a utilizar pueden contener caracteres o tokens innecesarios, por lo que deben ser eliminados antes de realizar alguna operación como la tokenización o normalización. Por ejemplo, etiquetas HTML, XML o JSON. 

Existen distintas formas de limpiar el texto con funciones como `clean_html()` de `nltk` o con la librería `BeautifulSoup`. También se pueden utilizar expresiones regulares, xpath o la librería lxml.

![Limpieza de datos](./data_cleaning.png)

## Identificación y eliminación de ruido

La noción de ruido en los textos depende siempre del contexto de análisis. En general, los datos en crudo suelen incluir elementos que no aportan valor al procesamiento, como etiquetas HTML, caracteres especiales, espacios repetidos o secuencias irrelevantes.

Las expresiones regulares son una herramienta útil para detectar y eliminar este ruido, permitiendo limpiar el texto y dejar únicamente la información relevante para las siguientes etapas del análisis.

Ejemplo: Usar una expresión regular para identificar todas las etiquetas HTML:

```python
import re

texto = "<p>Hola <b>mundo</b></p>"
limpio = re.sub(r"<.*?>", "", texto)
print(limpio)  # Resultado: Hola mundo
```

### Identificar ruido con RE



```python

text ="""
After viewing the [PINKIEPOOL Trailer](https://www.youtu.be/watch?v=ieHRoHUg)
it got me thinking about the best match ups.
<lb>Here's my take:<lb><lb>[](/sp)[](/ppseesyou) Deadpool<lb>[](/sp)[](/ajsly)
Captain America<lb>"""

import re

RE_SUSPICIUS = re.compile(r'[&#<>{}\[\]\\]')

def impurity(text, min_len=10):
    if text == None or len(text)< min_len:
        return 0
    else:
        return len(RE_SUSPICIUS.findall(text))/len(text)
    
print(impurity(text))
```

Salida:
```text
0.09009009009009009
```
El 9% de los caracteres son sospechosos de acuerdo con la definición de textos redactados correctamente. El patrón de búsqueda puede necesitar adaptaciones para corpora que contiene _hastags_ o token similares que contenga caracteres especiales.

Sin embargo, no necesita ser perfecto, solo necesitan ser lo suficientemente bueno para indicar una calidad potencial.

[Ejercicio - Identificación de ruido]()


[Ejemplo de identificación y eliminación de ruido]()

## Normalización de caracteres
Enmascaramiento de datos