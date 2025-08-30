# Desafío NLP - Clasificación de Emociones en Tweets

Este proyecto aborda el desafío de clasificación de emociones en publicaciones de Twitter/X, utilizando distintos enfoques de aprendizaje automático y modelos de lenguaje.

## Estructura del Proyecto

- `notebook/Desafío_NLP_Jeiner_Mendieta.ipynb`: Notebook principal con todo el flujo de trabajo, desde la carga de datos hasta la evaluación de modelos.

## Descripción del Flujo

1. **Instalación de Dependencias**
   - Se instalan versiones específicas de librerías para asegurar compatibilidad en Google Colab y evitar conflictos.

2. **Carga y Preprocesamiento de Datos**
   - Se clona el repositorio [EmoEvent](https://github.com/fmplaza/EmoEvent) y se cargan los splits de datos (`train`, `dev`, `test`) tanto en español como en inglés.
   - Se detectan automáticamente los separadores y columnas relevantes.
   - Se normalizan las etiquetas para asegurar consistencia.

3. **Modelos Implementados**
   - **Modelo 1: SVM lineal con TF-IDF**
     - Se entrena un pipeline de TF-IDF + LinearSVC para cada idioma.
     - Se evalúa el desempeño por clase y por evento.
   - **Modelo 2: XLM-RoBERTa (fine-tuning)**
     - Se utiliza `transformers` para ajustar un modelo multilingüe XLM-RoBERTa.
     - Se reportan métricas de accuracy y macro-F1, además de F1 por clase.
   - **GPT-4o-mini (zero/few-shot)**
     - Se evalúa el modelo GPT-4o-mini de OpenAI usando prompts y ejemplos (few-shot).
     - Se compara el desempeño con los modelos entrenados.

4. **Evaluación y Comparación**
   - Se presentan métricas de accuracy y macro-F1 para cada modelo e idioma.
   - Se discuten los resultados y posibles causas de diferencias de desempeño.

## Resultados Resumidos

| Modelo                | Accuracy | Macro-F1 |
|-----------------------|----------|----------|
| XLM-R en              | 0.698    | 0.376    |
| SVM en                | 0.645    | 0.391    |
| XLM-R es              | 0.358    | 0.182    |
| SVM es                | 0.353    | 0.177    |
| GPT-4o-mini en        | 0.357    | 0.272    |
| GPT-4o-mini es        | 0.140    | 0.093    |

- XLM-RoBERTa obtiene mejor accuracy en inglés, pero el macro-F1 es similar a SVM, indicando posibles problemas en clases minoritarias.
- El desempeño en español es considerablemente menor, sugiriendo desbalance o preprocesamiento insuficiente.
- GPT-4o-mini, al ser zero/few-shot y sin fine-tuning, tiene resultados modestos.

## Requisitos

- Python 3.8+
- Google Colab recomendado (por dependencias y GPU)
- API Key de OpenAI (para pruebas con GPT-4o-mini)

## Ejecución

1. Abre el notebook en Google Colab.
2. Ejecuta las celdas en orden.
3. Para usar GPT-4o-mini, coloca tu API Key de OpenAI donde se indica en el notebook.

## Créditos

- Notebook desarrollado por Jeiner Mendieta para el Desafío NLP.
- Datos: [EmoEvent](https://github.com/fmplaza/EmoEvent)