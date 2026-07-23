# DL-VisNIR-QualityClassifier: Clasificación de Calidad Agrícola mediante Espectroscopía Vis-NIR

[![GitHub](https://img.shields.io/badge/GitHub-Repositorio-blue?logo=github)](https://github.com/VivianaPM/DL-VisNIR-QualityClassifier)
[![Google Colab](https://img.shields.io/badge/Google_Colab-Manizana-orange?logo=googlecolab)](https://colab.research.google.com/drive/1-2rz1YxTOCJ78_Fn9vMA-BMM0cBTWqvn?usp=sharing)
[![Google Colab](https://img.shields.io/badge/Google_Colab-Champiñón-orange?logo=googlecolab)](https://colab.research.google.com/drive/1qNVkVKgUrr9MdItLzjC7wglg0bSVBQXR?usp=sharing#scrollTo=09454439)

## Problema / Objetivo

La calidad de productos agrícolas como manzanas y champiñones tradicionalmente se evalúa mediante inspección visual manual, lo que introduce subjetividad, variabilidad y altos costos operativos. Este proyecto propone una solución automatizada usando espectroscopía Vis-NIR (Visible - Near Infrared) combinada con redes neuronales profundas para clasificar calidad de manera objetiva y reproducible.

## Stack tecnológico

- **Lenguaje**: Python
- **Framework**: TensorFlow
- **Librerías**: Torch, Torchvision, Pandas, Numpy, Matplotlib, Scikit-learn y Seaborn

## Enfoque técnico

### Preparación de datos

Este proyecto es de índole restringida a un dataset de estudio gratuito **SpectroFood**.

**Preprocesamiento espectral:** Dado que el dataset ya viene pre-procesado por sus autores, se aplicaron únicamente ajustes menores:

- Eliminación de columnas no informativas (Apple y Mush No)
- Normalización
- Oversampling para balancear clases minoritarias

**Métricas de calidad:** Para la Actividad 2.4 se definieron las métricas estándar para evaluación de modelos de clasificación:

- Accuracy
- Precision
- Recall
- F1-Score

**Fuente del dataset:**

> Malounas, I., Vierbergen, W., Kutluk, S., Zude-Sasse, M., Yang, K., Zhao, M., Argyropoulos, D., Van Beek, J., Ampe, E., & Fountas, S. (2024). SpectroFood dataset: A comprehensive fruit and vegetable hyperspectral meta-dataset for dry matter estimation. Data in Brief, 52, 110040. https://doi.org/10.1016/j.dib.2024.110040

### Arquitectura del modelo

Tras la implementación del modelo soportado en redes neuronales para la clasificación de frutas y hortalizas mediante espectroscopia VIS-NIR, se evidenció el cumplimiento de los objetivos propuestos.

**Arquitectura óptima para manzanas:**

- Configuración: PA_A: [141, 64, 32, 1]
- Función de activación: tanh
- Optimizador: AdamW
- F1-Score: 77%
- Accuracy: 90%

**Arquitectura óptima para champiñones:**

- Configuración: PA_M: [206, 94, 32, 1]
- Función de activación: tanh
- Optimizador: AdamW
- F1-Score: 67%
- Accuracy: 73.2%

**Validación:** Estos resultados validan la viabilidad del enfoque para caracterización no invasiva de calidad, representando una contribución al campo de la agricultura de precisión.

### Entrenamiento

Se buscaba crear multiples estructuras de modelos predictivos para cada una de las muestras de estudio. A continuacion se describen los datos para el entrenamiento y resultado para los dos mejores modelos construidos.

- **Épocas**: Manzanas: 100 épocas / Champiñones: 100 épocas
- **Precisión alcanzada**: Manzanas: 90% / Champiñones: 73.2%

## ¿Cómo ejecutar el proyecto?

Acceder a los notebooks de Google Colab:

- **Modelo para Manzanas**: [Model Apple](https://colab.research.google.com/drive/1-2rz1YxTOCJ78_Fn9vMA-BMM0cBTWqvn?usp=sharing)
- **Modelo para Champiñones**: [Model Mushroom](https://colab.research.google.com/drive/1qNVkVKgUrr9MdItLzjC7wglg0bSVBQXR?usp=sharing#scrollTo=b605d07b)

---

[⬅ Volver al inicio](../index.md)
