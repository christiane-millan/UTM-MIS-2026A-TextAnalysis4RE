# Etiquetado POS (Part Of Speech)

El etiquetado de las partes del discurso (Part os Speech tagging o POS tagging) son categorías léxicas específicas a las cuales las palabras son asignadas basado en su contexto sintáctico y rol (pronombre, verbos, adjetivo y adverbio).

El etiquetado POS (Part-of-Speech Tagging) es el proceso de asignar a cada palabra de un texto su categoría gramatical, como sustantivo, verbo, adjetivo, adverbio, pronombre, entre otras.

Ejemplo

>The cat is sleeping on the sofa.

Etiquetado POS:
- The → Determiner (DET)
- cat → Noun (NOUN)
- is → Verb (AUX)
- sleeping → Verb (VERB)
- on → Preposition (ADP)
- the → Determiner (DET)
- sofa → Noun (NOUN)

Importancia del POS tagging

- Permite analizar la estructura sintáctica de una oración.
- Es la base para tareas más avanzadas como:
- Lematización: conocer si una palabra es verbo, sustantivo o adjetivo ayuda a obtener su forma base correcta.
- Extracción de información: identificar nombres propios, entidades o relaciones.
- Traducción automática: distinguir el rol de cada palabra para generar una traducción más precisa.

[Ejemplo](./code/pos.ipynb)