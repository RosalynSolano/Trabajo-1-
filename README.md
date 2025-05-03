# Breast Cancer Prediction App

## Descripción

Aplicación de machine learning que predice si un tumor es benigno o maligno utilizando un modelo de regresión logística entrenado con el dataset de cáncer de mama de Wisconsin.

Incluye:
- Reentrenamiento del modelo con retraining.py.
- Automatización del proceso mediante GitHub Actions y CML.
- Construcción de imagen Docker para despliegue.

## Requisitos

- Python 3.10 o superior
- Docker Desktop (opcional para despliegue en contenedores)

## Variables de entrada

El modelo utiliza variables numéricas extraídas de imágenes de células mamarias, incluyendo:

- radius_mean
- texture_mean
- perimeter_mean
- area_mean
- smoothness_mean
- compactness_mean
- concavity_mean
- concave points_mean
- symmetry_mean
- fractal_dimension_mean
- entre otras características derivadas.

## Salida del modelo

- 0: Tumor benigno.
- 1: Tumor maligno.

## Instrucciones para uso local

1. Clonar el repositorio:

```bash
git clone https://github.com/ignaciocastillo/tarea4.git
cd tarea4
Crear y activar un entorno virtual:

bash
Copiar
Editar
python -m venv .venv
.\.venv\Scripts\activate
Instalar las dependencias:

bash
Copiar
Editar
pip install -r requirements.txt
Ejecutar la aplicación:

bash
Copiar
Editar
streamlit run app.py
Acceder a la aplicación en:

arduino
Copiar
Editar
http://localhost:8501
Reentrenar el modelo manualmente:

bash
Copiar
Editar
python retraining.py
Esto actualizará el modelo en model/logistic_regression_model.pkl y el reporte de métricas.

Instrucciones para despliegue con Docker
Construir la imagen Docker:

bash
Copiar
Editar
docker build -t breast-cancer-app .
Ejecutar el contenedor Docker:

bash
Copiar
Editar
docker run -p 8501:8501 breast-cancer-app
Acceder a la aplicación en:

arduino
Copiar
Editar
http://localhost:8501
Automatización
Cada vez que se realiza un push a la rama main, el flujo de trabajo de GitHub Actions ejecuta:

Reentrenamiento automático del modelo.

Generación de métricas mediante CML.

Publicación de los reportes en el repositorio.

Es necesario configurar un secreto llamado REPO_TOKEN en el repositorio de GitHub para habilitar la autenticación automática en los flujos de trabajo.

yaml
Copiar
Editar



---
