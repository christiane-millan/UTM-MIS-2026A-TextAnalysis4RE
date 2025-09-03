# Introducción 

## Análisis de texto

El análisis de textos es el proceso de examinar y descomponer un conjunto de escritos con el fin de identificar patrones, estructuras, significados y relaciones dentro del lenguaje. Es una disciplina que combina aspectos de la lingüística, la informática y la estadística, y que se aplica tanto en humanidades digitales como en áreas tecnológicas como la minería de datos y el procesamiento de lenguaje natural (PLN).

A diferencia de una simple lectura, el análisis de textos busca ir más allá de la interpretación superficial, empleando métodos sistemáticos que permiten descubrir información implícita, tendencias o regularidades.

## Documentos

Un documento de texto es una secuencia de caracteres para poder construir modelos sobre el contenido es necesario realizar la transformación el texto en una secuencia de palabras o secuencias significativas de caracteres llamadas tokens. 


## Expresiones Regulares

Las expresiones regulares (también conocidas como regex o regexp) son patrones que permiten describir, buscar y manipular cadenas de texto de manera muy flexible y precisa. Se utilizan ampliamente en programación, análisis de datos y procesamiento de lenguaje natural, ya que facilitan tareas como validar formatos, extraer información específica o realizar sustituciones dentro de un texto.

En lugar de buscar coincidencias exactas (por ejemplo, la palabra “casa”), una expresión regular describe un patrón general que puede aplicarse a múltiples casos (por ejemplo, “cualquier palabra que empiece con c y termine con a”).

[Buscar y reemplazar](./code/01-1_intro_regex.ipynb)

## Notación de expresiones regulares

Características principales:

- **Definición de patrones**: se construyen con combinaciones de caracteres normales (como letras y números) y caracteres especiales (como . * + ? [] () |), que tienen significados particulares.
- **Flexibilidad**: permiten encontrar coincidencias simples (como “hola”) o muy complejas (como “cualquier dirección de correo electrónico válida”).
- **Reusabilidad:** un patrón bien diseñado puede aplicarse en distintos lenguajes de programación o herramientas, ya que la mayoría soporta expresiones regulares.

[Notación de RegEx](./code/01-2_regex_fundamentals.ipynb)

En resumen, las expresiones regulares son como un lenguaje especializado dentro del lenguaje de programación que permite trabajar con texto de manera eficiente, ahorrando tiempo en comparación con métodos tradicionales de búsqueda o validación.
