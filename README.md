# Desafío NLP: Clasificación de Emociones en Tweets (EmoEvent)

Este proyecto aborda la clasificación de emociones en tweets en español usando el dataset [EmoEvent](https://github.com/fmplaza/EmoEvent). Se comparan tres enfoques de modelado:

- **GPT-4o (OpenAI)**
- **BERT Multilingüe**
- **BiLSTM (Keras/TensorFlow)**

## Estructura del Proyecto

- `notebook/NLP_Jeiner_Mendieta.ipynb`: Notebook principal con todo el flujo de trabajo.
- `emoevent_data/es/`: Carpeta con los datos descargados (`train.tsv`, `dev.tsv`, `test.tsv`).
- Resultados y métricas exportados a CSV.

## Flujo de Trabajo

1. **Descarga y exploración de datos**  
   Se descargan los splits de EmoEvent y se explora la distribución de emociones y eventos.

2. **Modelo 1: GPT-4o (OpenAI)**
   - Clasificación de emociones usando la API de OpenAI.
   - Evaluación sobre una muestra de 50 tweets.

3. **Modelo 2: BERT Multilingüe**
   - Entrenamiento y evaluación de un modelo BERT desde cero.
   - Balanceo de clases, métricas y matrices de confusión.

4. **Modelo 3: BiLSTM**
   - Tokenización y entrenamiento de un modelo BiLSTM.
   - Evaluación y comparación con los otros modelos.

5. **Comparación de modelos**
   - Comparativa de predicciones en ejemplos reales.

## Requisitos

- Python 3.8+
- Paquetes: `pandas`, `scikit-learn`, `matplotlib`, `torch`, `transformers`, `tensorflow`, `tqdm`, `openai`
- API Key de OpenAI (para GPT-4o)

Instalación rápida de dependencias principales:
```bash
pip install pandas scikit-learn matplotlib torch transformers tensorflow tqdm openai
```

## Ejecución

Abre el notebook y sigue las celdas en orden.  
**Nota:** No subas tu API Key a ningún repositorio.

## Créditos

- Dataset: [EmoEvent](https://github.com/fmplaza/EmoEvent)
- Autor: Jeiner Mendieta

---

¡Siéntete libre de modificar este README según tus