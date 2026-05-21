# Proyecto Final IA
Proyecto final para la materia de Inteligencia Artificial que trata sobre el reconocimiento de emociones faciales basado en un "Vision Transformer Small (ViT-Small)" desarrollado por Sofía Jaramillo y Juan Esteban Toro.

# Reconocimiento de Emociones Faciales con Vision Transformer (ViT)
Este proyecto implementa un modelo **Vision Transformer (ViT-Small/16)** preentrenado en ImageNet-21k para clasificar expresiones faciales en siete emociones: **Happy, Surprise, Sad, Anger, Disgust, Fear, Neutral**. Utiliza el dataset **AffectNet** y aplica técnicas avanzadas como fine-tuning en dos fases, WeightedRandomSampler, label smoothing, cosine annealing y early stopping.

## Estructura del repositorio

- `vit_emotion_recognition.ipynb` — Notebook principal con todo el código (entrenamiento, evaluación, visualización).
- `requirements.txt` — Dependencias necesarias.
- `outputs` — Carpeta donde se guardan los resultados (gráficas, métricas, mejor modelo).

## Dataset: AffectNet

El dataset utilizado es **AffectNet**, que contiene aproximadamente 280,000 imágenes faciales etiquetadas con 7 emociones básicas.

- **Enlace de descarga (Kaggle):** [AffectNet Dataset](https://www.kaggle.com/datasets/mstjebashazida/affectnet)
- **Estructura esperada dentro del archivo descargado:**
```text
affectnet/
├── Train/
│   ├── happy/
│   ├── sad/
│   ├── anger/
│   └── ... (resto de emociones)
├── Test/
│   ├── happy/
│   └── ...
```
- **Nota:** El código está preparado para leer las carpetas con nombres en minúscula (happy, sad, anger, surprise, disgust, fear, neutral).

## Instrucciones para ejecutar el código en Kaggle
El proyecto fue diseñado para ejecutarse en **Kaggle** con acelerador GPU (T4 o P100). Sigue estos pasos:

### 1. Subir el dataset a Kaggle
- Ve a [Kaggle](https://www.kaggle.com/), inicia sesión.
- Crea un nuevo **Dataset** (sección "Data" → "New Dataset").
- Sube la carpeta `affectnet` con la estructura anterior. Nombra el dataset como `affectnet` (o el nombre que prefieras).
- Una vez subido, ve a la pestaña "Data" de tu notebook y haz clic en "Add Data" para añadir este dataset.

### 2. Notebook en Kaggle
- Abre este link: https://www.kaggle.com/code/sofiajch07/vit-emotion-recognition/notebook
- Dale click en **Editar**
- En **Settings** (icono de engranaje), activa **GPU** (T4 o P100).

### 3. Instalar dependencias
- El notebook ya contiene celdas para instalar `timm`, `scikit-learn`, etc. Si prefieres usar el archivo `requirements.txt`, súbelo al entorno de Kaggle y ejecuta:
```python
!pip install -r requirements.txt
```

### 4. Ejecutar el notebook
- Correr las celdas en orden

### 5. Resultados
Se guardan en la carpeta de outputs:

training_curves.png — Curvas de pérdida y accuracy.
confusion_matrix.png — Matriz de confusión.
roc_curves.png — Curvas ROC por clase.
attention_maps.png — Mapas de atención visualizados.
final_metrics.json — Resumen de métricas (accuracy, F1, ROC-AUC, etc

### Manigiest de uso de IA
Herramientas utilizadas: ChatGPT (OpenAI) – modelo GPT-4.
Propósito del uso: Asistencia en la depuración de código, buenas prácticas y redacción.

Partes del proyecto soportadas por IA:
-Código: Corrección de errores en la captura de matrices de atención.
-Documentación: Redacción del presente README, generación de la estructura del repositorio.
- Experimentación: Recomendación de hiperparámetros (tasas de aprendizaje, patience, freeze_epochs).

La IA se utilizó como apoyo para superar obstáculos técnicos específicos y para optimizar la claridad de la documentación.
