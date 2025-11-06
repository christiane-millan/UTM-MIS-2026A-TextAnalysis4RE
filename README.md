# Análisis de texto para ingeniería de requisitos

Universidad Tecnológica de la Mixteca

## Maestría en Ingeniería de Software

Dr. Millán

## Objetivo

Presentar al estudiante técnicas, herramientas y tecnologías de análisis de textos que se pueden aplicar a distintos documentos de requisitos de software para automatizar una serie de tareas de análisis lingüístico realizadas en las distintas fases de la Ingeniería de Requerimientos.

## Requisitos

    - Python 3.11
    - Entornos de trabajo en Python

Instalar ambiente con `conda`:

```bash
> conda env --file environment.yml  
```

Exportar ambiente con `conda`:
```python
> conda list --export > requirements.yml
```

## Contenido

### 1. Introducción

- [`Análisis de texto`](./01-intro/README.md)
- [`Expresiones Regulares`](./01-intro/README.md)
  
### 2. Procesamiento y comprensión de requisitos de software

- [Pandas](./02-processing_understanding/00-previos/00_numpy_pandas.ipynb)

#### Limpieza de datos
- [`2.1 Limpieza de datos con RE`](./02-processing_understanding/01-data_cleaning/README.md)

#### Procesamiento lingüístico
- [`2.2 Tokenización`](./02-processing_understanding/02-tokenization/README.md)
- [`2.3 Steaming`](./02-processing_understanding/03_stemming/README.md)
- [`2.4 Lematización`](./02-processing_understanding/04-lemmatization/README.md)
- [`2.5 Stopwords`](./02-processing_understanding/05-stopwords/README.md)
- [`2.6 Etiquetado POS`](./02-processing_understanding/06-Pos/REDME.md)
- [`2.7 Reconocimiento de Entidades Nombradas (NER)`](./02-processing_understanding/07-NER/README.md)
- [Análisis Exploratorio de Datos](./02-processing_understanding/08-EDA/README.md)

#### Representación de texto

- [`Conteo de palabras`](./03-features_extraction/01-bow/README.md)
- [`TF-IDF`](./03-features_extraction/02-tf-idf/README.md)
- [`N-gramas`](./03-features_extraction/03-ngrams/README.md)
- [Análisis Exploratorio de Datos - Parte II](./03-features_extraction/04-EDA/code/eda_tfidf_ngrams.ipynb)

### [3. Clasificación de requisitos](./04-text_classification/README.md)

#### Extracción de características

- [`One-hot`](./04-text_classification/04-1_feature_engineering/04-1-1_onehot/REAME.md)
- [`Bolsa de palabras`]()
- [`TF-IDF`]()
- [Reducción de dimensiones]()

#### Algoritmos de clasificación

- [Naive Bayes]()
- [Regresión Logística](./04-text_classification/04-2_text_class/04-2-2-_lr/README.md)
  - Regresión Logística con BoW
  - Regresión Logística con TF-IDF

- [SVM](./04-text_classification/04-2_text_class/04-2-3_svm/)
  - LinearSVC
  - imbalanced-learn 
  

### 4. Similitud y agrupación de requisitos
