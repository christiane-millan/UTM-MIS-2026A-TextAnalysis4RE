# Stopwords o palabras vacías

En los texto existen palabras que aparecen con muchísima frecuencia pero que, por sí solas, aportan poco valor semántico al análisis. A estas palabras se les conoce como palabras vacías (_stopwords_).

Ejemplos comunes en español:

- **Artículos**: el, la, los, las, un, una
- **Preposiciones**: de, en, con, para, por
- **pronombres**: yo, tú, él, ella, nosotros

Ejemplos comunes en inglés:

- **Artículos**: the, a, an
- **Preposiciones**: in, on, at, by
- **Pronombres**: he, she, they, we

Aunque estas palabras son importantes para la gramática, en muchos procesos de procesamiento de lenguaje natural (PLN) se eliminan para centrarse en las palabras con mayor carga semántica.

>The students are working on a new project in the university.

- Palabras vacías: the, are, on, a, in, the
- Palabras con significado relevante: students, working, new, project, university

>students working new project university

[Ejemplo stopwords](./code/stopwords.ipynb)
[Ejemplo stopwords]() 

Ejemplo de tokenize, stopwords y steaming (visualizar)
Lo mismo con lematización