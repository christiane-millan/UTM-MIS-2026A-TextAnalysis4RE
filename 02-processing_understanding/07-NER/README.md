# Named Entity Recognition

Named Entity Recognition (NER) es la tarea de detectar y etiquetar menciones de entidades en texto (p. ej., PERSON, LOCATION, ORGANIZATION, DATE). Es clave en pipelines de PLN porque permite estructurar texto libre para tareas como extracción de información, QA o análisis de noticias.
	•	Entrada: texto sin estructura.
	•	Salida: spans de texto con etiquetas de tipo de entidad.
	•	Ejemplos: “Barack Obama (PERSON) nació en Hawái (GPE) en 1961 (DATE).”

Nota: El chunker preentrenado de NLTK funciona bien como demo, principalmente para inglés y en textos generales; para español o producción, suele rendir mejor spaCy o modelos de Hugging Face.

[Ejemplo NER](./code/ner.ipynb)