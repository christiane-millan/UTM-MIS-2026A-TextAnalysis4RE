# Stemming

## Morfología

- Los **morfemas** son las unidades más pequeñas con significado en un lenguaje natural.

    Ejemplo: en la palabra niños, hay dos morfemas: niñ- (raíz) y -os (marca de plural).
  
## Tipos de morfemas

- **Raíces (base form)**: son la parte fundamental de una palabra, la que aporta el significado principal.

> Ejemplo: en comer, la raíz es com-.

- **Afijos**: son unidades que se añaden a la raíz para modificar o ampliar su significado.
- **Prefijos**: se colocan al inicio (des-hacer, re-escribir).
- **Sufijos**: se colocan al final (papel-ero, flor-al).

También existen infixes (infijos, en otras lenguas) o circumfixes, menos comunes en español.

La **flexión** es el proceso de formar nuevas palabras a partir de la raíz y afijos, ajustando la palabra según género, número, tiempo verbal, etc.

> Ejemplo: cantar → cant-amos, cant-aría, cant-aste.

El **stemming** es el proceso inverso: reducir una palabra a su forma base o raíz aproximada. 

> Ejemplo: jugando, jugaría y jugaron → todas se reducen a la raíz jugar.

En otros términos, el _stemming_ es un método de normalización de texto utilizado en NLP para simplificar el texto antes de que sea procesado por un modelo. Al romper los últimos caracteres de una palabra para encontrar una forma común de la palabra.



[Ejemplo 4. Stemming](./code/stemming.ipynb)