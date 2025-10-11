# NLP_Practice

Este repositorio recopila una serie de desafíos prácticos de Procesamiento de Lenguaje Natural (NLP) para la cátedra homónima de la Carrera de Especialización en Inteligencia Artificial. Los desafíos están orientados a aplicar distintas técnicas de representación, modelado y generación de texto.
Cada notebook aborda una etapa en la evolución de un pipeline NLP moderno, desde la vectorización tradicional hasta el entrenamiento de modelos secuenciales tipo encoder-decoder y, como desafío adicional, la construcción de un bot conversacional.

---

## Desafío 1 — Vectorización de documentos y similitud

### Objetivo

Explorar la representación vectorial de textos mediante la técnica *TF-IDF* y analizar la similitud semántica entre documentos.

### Desarrollo

Se utiliza el dataset *20 Newsgroups* de **Scikit-learn**, con 20 categorías temáticas.

Los documentos se vectorizan mediante TF-IDF (Term Frequency - Inverse Document Frequency), se calculan las similitudes entre documentos seleccionados y el resto del corpus, analizando si los textos más cercanos pertenecen a la misma categoría.

### Técnicas aplicadas

* Vectorización TF-IDF

* Cálculo de similitud

* Análisis exploratorio de contenido y etiquetas

---

## Desafío 2 — Word Embeddings 

### Objetivo

Entrenar modelos de word embeddings propios utilizando la librería Gensim, aplicándolos a corpus textuales personalizados.

### Desarrollo

Se trabajan dos corpus: letras de canciones de Britney Spears y Taylor Swift.

Se realiza la limpieza y tokenización del texto con *nltk* y *tensorflow*. Luego se entrena un modelo **Word2Vec** con arquitectura *Skip-Gram*, generando representaciones vectoriales que capturan relaciones semánticas entre palabras. Por último, se comparan similitudes entre términos y contextos de ambos artistas, extrayendo conclusiones sobre la visión que tiene cada artista sobre temáticas comunes.

### Técnicas aplicadas

* Limpieza y tokenización con NLTK

* Entrenamiento de embeddings Word2Vec (Usando Skip-Gram)

* Análisis de similitud y analogías semánticas

---

## Desafío 3 — Modelo de Lenguaje con LSTM

### Objetivo

Construir un modelo de lenguaje basado en redes neuronales recurrentes (RNN, LSTM y GRU) capaz de predecir secuencias de texto en español. Comparar los resultados obtenidos entre los modelos.

### Desarrollo

Corpus utilizado: "Rebelión en la granja" de George Orwell.

Se extrae y limpia el texto desde un archivo EPUB, se genera un vocabulario e índices de palabras y se entrena un modelo LSTM para predecir la siguiente palabra en una secuencia, monitoreando la perplejidad como métrica principal. Este modelo es utilizado como baseline de comparación entre los otros modelos planteados.

### Técnicas aplicadas

* Tokenización y mapeo de vocabulario

* Modelos recurrentes (SimpleRNN, LSTM, GRU)

* Optimización con RMSprop

* Evaluación por perplejidad

---

## Desafío 4 — Traductor Inglés ↔ Español (Encoder–Decoder LSTM)

### Objetivo

Desarrollar un modelo seq2seq (encoder–decoder) basado en LSTM para traducir frases del inglés al español.

### Desarrollo

Se utiliza el dataset *Anki English–Spanish Phrases*, pasándolo por un proceso de normalización, tokenización y adición de tokens especiales en cada línea de vocabulario para poder generar un dataloader con esta información. Luego se implementa un modelo encoder-decoder con capas LSTM y mecanismos de atención para finalmente hacer una inferencia en la traducción de una frase determinada.

### Técnicas aplicadas

* Preprocesamiento y limpieza de corpus paralelo

* Modelado seq2seq con LSTM

* Embeddings y padding de secuencias

* Entrenamiento supervisado con validación

---

## Desafío Extra — Bot Conversacional (QA Bot)

### Objetivo

Extender el enfoque del traductor para crear un bot de preguntas y respuestas (QA) basado en LSTM.

### Desarrollo

Se utiliza el dataset *ConvAI2* (Conversational Intelligence Challenge 2), con más de 4.700 diálogos reales entre humanos y bots.

Se preprocesan los textos para extraer pares pregunta–respuesta, se entrena un modelo encoder–decoder con embeddings FastText y unidades LSTM siguiendo el pipeline desarrollado en el desafío 4.

### Técnicas aplicadas

* Preprocesamiento de dataset conversacional

* Embeddings FastText

* Arquitectura LSTM encoder–decoder

* Entrenamiento supervisado y prueba con ejemplos de diálogo

---

# Tecnologías principales utilizadas en este repositorio

Lenguaje: Python

Librerías: Scikit-learn · NLTK · TensorFlow · Keras · Gensim · Pandas · NumPy

Modelos: TF-IDF, Word2Vec, LSTM, GRU, Seq2Seq

Datasets: 20 Newsgroups · Taylor Swift / Britney Spears lyrics · Rebelión en la granja · Anki English–Spanish · ConvAI2
