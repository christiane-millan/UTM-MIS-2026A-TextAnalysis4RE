# 5.1. Modelado de tópicos

## Non-Negative Matrix Factorization (NMF): una introducción

La **Non-Negative Matrix Factorization (NMF)**, o **Factorización de Matrices No Negativas**, es una técnica de reducción de dimensionalidad que busca representar una matriz original como el producto de dos matrices más pequeñas, con la particularidad de que **todos sus valores deben ser no negativos** (≥ 0).

Su objetivo es descubrir **estructuras latentes** en los datos, es decir, patrones ocultos que permiten comprender mejor la información y trabajar con ella de forma más eficiente.

**Idea fundamental**

Dada una matriz original $V \in \mathbb{R}_{\ge 0}^{m \times n}$ (por ejemplo, una matriz documento-término en PLN), NMF busca dos matrices:

- $W \in \mathbb{R}_{\ge 0}^{m \times k}$ 
- $H \in \mathbb{R}_{\ge 0}^{k \times n}$

tales que:

$V \approx WH$

donde:

- $k$ es la **dimensión latente**, típicamente mucho menor que $m$ o $n$,
- $W$ contiene los **componentes latentes**,
- $H$ contiene las **representaciones de los datos en ese espacio reducido**.

La restricción de no negatividad hace que NMF produzca una descomposición **partes-basada**.

Esto significa que los datos se representan como combinaciones **aditivas** de componentes básicos, algo más natural en muchos contextos. Ejemplos:

- En imágenes: los pixeles no pueden tener valores negativos → las partes de un rostro (ojos, boca, nariz) se suman.
- En texto: las frecuencias de palabras son no negativas → los temas se forman como sumas de palabras.

La interpretación de los resultados es más intuitiva que en otras técnicas como PCA (que permite valores negativos en los componentes).

### Aplicaciones principales

**a) Procesamiento de lenguaje natural (PLN)**

- **Modelado de temas (Topic Modeling)**: cada documento se expresa como combinación de temas, y cada tema como combinación de palabras.  
- **Reducción de dimensionalidad** para tareas de clasificación o clustering.
- **Extracción de tópicos interpretables** en grandes corpus de documentos.

**b) Visión por computadora**

- Representación de imágenes mediante partes.
- Reconocimiento facial parcial.

**c) Análisis musical**

- Separación de fuentes de audio y mezcla de señales.

**d) Sistemas recomendadores**

- Descomposición de matrices usuario-item para representar preferencias latentes.

### Interpretación en modelos de temas

Para PLN, la matriz documento-término $V$ se factoriza así:

- Las columnas de $W$ representan **temas**.
- Las filas de $H$ representan **documentos** en términos de mezcla de esos temas.

Así, NMF funciona como un **topic model determinista**, donde cada tema es un conjunto de palabras con pesos no negativos y fácilmente interpretables.


### Ventajas de NMF

- **Alta interpretabilidad**: los componentes tienen sentido semántico.
- **Simplicidad computacional** comparada con modelos probabilísticos como LDA.
- Funciona bien con datos dispersos (sparse).
- Excelentes resultados para **clustering y clasificación** en texto.


### Limitaciones

- No garantiza una única solución óptima; depende de la inicialización.
- No maneja explícitamente la naturaleza probabilística del texto (como sí LDA).
- La elección del parámetro $k$ no es trivial.

## Singular Value Decomposition (SVD)

La **Descomposición en Valores Singulares** (*Singular Value Decomposition*, SVD), al igual NNF, es un método fundamental en álgebra lineal que permite descomponer una matriz $A$ en tres matrices que revelan su estructura interna. Esta técnica es ampliamente utilizada en análisis de datos, reducción de dimensionalidad y procesamiento de lenguaje natural (PLN).

### Definición formal

Sea una matriz $A \in \mathbb{R}^{m \times n}$, su SVD viene dado por:

$A = U \, \Sigma \, V^{T}$

donde:

- $U$ es una matriz ortogonal $m \times m$ cuyos vectores columna son los **vectores singulares izquierdos**.
- $\Sigma$ es una matriz diagonal $m \times n$ cuyos elementos son los **valores singulares**.
- $V^{T}$ es la traspuesta de una matriz ortogonal $n \times n$ cuyas filas son los **vectores singulares derechos**.


Los valores singulares indican la importancia de cada componente latente. Ordenados de mayor a menor, permiten identificar qué dimensiones contienen más información relevante.

### Aplicaciones en PLN

1. __Latent Semantic Analysis (LSA):__ Aplicar SVD a una matriz término-documento permite descubrir **relaciones semánticas latentes**, incluso cuando las palabras no coocurren directamente.

2. __Reducción de dimensionalidad:__ Para un valor reducido $k$

$A_k = U_k \, \Sigma_k \, V_k^{T}$

Con esto se conserva la estructura principal de la matriz con menos dimensiones.

3. __Sistemas recomendadores:__ SVD permite identificar patrones latentes en las preferencias de usuarios usando matrices de calificaciones.

## LDA (Latent Dirichlet Allocation)

Latent Dirichlet Allocation (LDA) es un **modelo probabilístico generativo** utilizado en **Procesamiento de Lenguaje Natural (PLN)** para realizar **modelado de temas** (*topic modeling*). Su propósito es **descubrir automáticamente los temas ocultos** dentro de una colección grande de documentos sin necesidad de etiquetas.

LDA se basa en dos ideas principales:

1. **Cada documento** está compuesto por una mezcla de varios **temas**.
2. **Cada tema** es una distribución de **palabras** que suelen aparecer juntas.

Gracias a esto, LDA es un método eficaz para organizar, resumir y explorar textos en grandes volúmenes.

**Intuición del funcionamiento**

LDA propone un proceso hipotético mediante el cual los documentos fueron generados:

1. Cada documento tiene una mezcla particular de temas.
2. Cada tema tiene una probabilidad de contener ciertas palabras.
3. Para cada palabra del documento:
   - Se elige un **tema** de acuerdo con la mezcla del documento.
   - Se elige una **palabra** según las probabilidades del tema seleccionado.

El algoritmo realiza el proceso inverso: **dado un conjunto de textos ya escritos, infiere** qué temas y distribuciones pudieron haber generado esos documentos.


### **Fundamento matemático (básico)**

LDA utiliza distribuciones **Dirichlet** para modelar las variaciones:

- Distribución de temas por documento:  
  $\theta_d \sim \text{Dirichlet}(\alpha)$

- Distribución de palabras por tema:  
  $\phi_k \sim \text{Dirichlet}(\beta)$

Para cada palabra $w$ del documento:

- Selección de un tema:  
  $z_{d,n} \sim \text{Multinomial}(\theta_d)$

- Selección de una palabra dentro de ese tema:  
  $w_{d,n} \sim \text{Multinomial}(\phi_{z_{d,n}})$


### ¿Para qué se utiliza LDA?

- Descubrir temas dominantes en corpus extensos  
- Resumir colecciones de documentos  
- Análisis de sentimientos y opiniones  
- Agrupación de noticias, reportes, artículos científicos, blogs, etc.  
- Exploración de contenido en redes sociales  
- Reducción de dimensionalidad en tareas de texto  

### Ventajas

- No requiere etiquetas (método no supervisado).
- Produce **temas interpretables** por humanos.
- Funciona bien con corpus grandes.
- Es un buen punto de entrada antes de usar modelos más avanzados.

### Limitaciones

- Requiere definir manualmente el número de temas.
- Basado en **Bag of Words**, por lo que no captura orden ni contexto semántico profundo.
- Puede generar temas muy similares si no se ajustan bien los hiperparámetros.
- Superado en precisión por métodos modernos basados en embeddings (BERT, SBERT, BERTopic).

[Ejemplo Modelado tópicos](./code/topic_modeling.ipynb)

