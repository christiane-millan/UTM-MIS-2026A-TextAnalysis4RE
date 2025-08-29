# Lematización

El proceso de lematización es muy similar al stemming, ya que en ambos casos se eliminan afijos (prefijos o sufijos) para obtener una forma base de la palabra.

La diferencia principal está en la precisión del resultado:

- **Stemming**: reduce una palabra a su raíz (stem), pero esta raíz no siempre corresponde a una palabra correcta en el idioma.

> Ejemplo: studies → studi, playing → play, better → bett

- **Lematización**: obtiene el lema, es decir, la forma base reconocida en el diccionario.

>Ejemplo: studies → study, playing → play, better → good

- El _stem_ puede no ser una palabra válida.
- El _lema_ siempre corresponde a una palabra existente en el diccionario.


[Ejemplo 5. Lematización](./code/lemmatization.ipynb)