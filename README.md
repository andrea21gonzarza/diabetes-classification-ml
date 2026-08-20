# Clasificación de pacientes con diabetes mediante aprendizaje automático

## Descripción del proyecto

Este proyecto desarrolla y evalúa modelos de aprendizaje automático para la clasificación de pacientes en función de la presencia o ausencia de diabetes, utilizando variables clínicas y demográficas.

El análisis incluye preprocesamiento de los datos, análisis exploratorio, entrenamiento y comparación de modelos, validación cruzada, optimización de hiperparámetros, análisis del umbral de clasificación y simulación del modelo con nuevos perfiles.

## Dataset

El conjunto de datos contiene 768 observaciones y ocho variables predictoras:

- Pregnancies
- Glucose
- BloodPressure
- SkinThickness
- Insulin
- BMI
- DiabetesPedigreeFunction
- Age

La variable objetivo es Outcome:

- 0: clase negativa
- 1: clase positiva

## Modelos evaluados

Se evaluaron tres algoritmos de clasificación:

1. Regresión logística
2. Árbol de decisión
3. Random Forest

Posteriormente, los modelos seleccionados fueron sometidos a validación y optimización de hiperparámetros.

## Modelo final

El modelo seleccionado fue un Random Forest optimizado con:

- n_estimators = 100
- max_depth = 5
- min_samples_split = 5
- min_samples_leaf = 2

Se seleccionó un umbral de clasificación de 0.40.

### Rendimiento final

| Métrica | Resultado |
|---|---:|
| Accuracy | 0.747 |
| Precisión | 0.615 |
| Sensibilidad | 0.741 |
| Especificidad | 0.750 |
| F1-score | 0.672 |
| ROC-AUC | 0.818 |

## Simulación de nuevos pacientes

Se realizó una simulación utilizando tres perfiles construidos a partir de los percentiles 25, 50 y 75 de las variables predictoras.

Para SkinThickness e Insulin, los percentiles se calcularon excluyendo los valores iguales a cero.

| Perfil | Probabilidad estimada | Clasificación |
|---|---:|---:|
| Perfil 1 | 0.029 | 0 |
| Perfil 2 | 0.331 | 0 |
| Perfil 3 | 0.646 | 1 |

Las clasificaciones se realizaron utilizando el umbral final de 0.40.

## Requisitos

Las dependencias necesarias se encuentran especificadas en el archivo requirements.txt.

Para instalar las dependencias:

    pip install -r requirements.txt

## Ejecución

1. Descargar o clonar el repositorio.
2. Instalar las dependencias especificadas en requirements.txt.
3. Asegurarse de que el conjunto de datos se encuentre disponible.
4. Abrir diabetes_classification.ipynb.
5. Ejecutar las celdas del notebook en orden.

## Limitaciones

Los resultados corresponden al conjunto de datos utilizado en este proyecto y no constituyen una validación clínica del modelo.

Antes de considerar su aplicación en un entorno real sería necesaria una validación externa utilizando datos independientes y procedentes de otras poblaciones.

## Uso académico

Este proyecto fue desarrollado con fines académicos como parte de un Trabajo de Fin de Máster relacionado con la aplicación de inteligencia artificial en el ámbito sanitario.
