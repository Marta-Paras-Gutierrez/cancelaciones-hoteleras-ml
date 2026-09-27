# 🏨 Predicción de Cancelaciones de Reservas Hoteleras

Modelo de machine learning desarrollado para predecir, en el momento de la reserva, la probabilidad de que un cliente cancele, pensado desde la perspectiva del equipo de Revenue Management de una cadena hotelera con dos propiedades en Portugal.

## 📊 Resumen del proyecto

Este proyecto transforma datos históricos de reservas hoteleras en un sistema de predicción y aviso de riesgo de cancelación, utilizando Python y técnicas de machine learning supervisado.

El trabajo incluye análisis exploratorio de datos, limpieza y tratamiento de valores nulos y anomalías, ingeniería de variables, entrenamiento y comparación de varios modelos de clasificación, gestión del desbalanceo de clases, optimización de hiperparámetros e interpretabilidad del modelo mediante SHAP.

## 🎯 Objetivos

- Analizar los patrones de cancelación según el tipo de hotel, el mes, el canal de distribución y la antelación de la reserva.
- Detectar y eliminar variables con fuga de información antes del modelado.
- Entrenar y comparar distintos modelos de clasificación para predecir la cancelación.
- Corregir el desbalanceo entre reservas canceladas y no canceladas.
- Optimizar el modelo mediante una búsqueda de hiperparámetros.
- Explicar las predicciones del modelo mediante interpretabilidad SHAP.
- Traducir el modelo en un sistema de aviso de riesgo con impacto económico estimado.

## 🛠️ Herramientas y tecnologías

- **Python**
- **pandas** y **NumPy**
- **scikit-learn**
- **XGBoost**
- **Optuna** (optimización de hiperparámetros)
- **SHAP** (interpretabilidad)
- **imbalanced-learn**
- **Matplotlib** y **Seaborn**
- Jupyter Notebook

## 📁 Fuente de datos

El dataset utilizado es:

**Hotel Booking Demand** — Antonio, N., Almeida, A. & Nunes, L. (2019). *Data in Brief*, 22, 41–49.

[Hotel Booking Demand – Kaggle](https://www.kaggle.com/datasets/jessemostipak/hotel-booking-demand)

Cerca de 119.000 reservas de dos hoteles entre julio de 2015 y agosto de 2017. El archivo CSV original no se incluye en este repositorio.

## 🧩 Proceso seguido

- Análisis exploratorio y comprobación de coherencia de los datos (huéspedes, duplicados, valores nulos).
- Eliminación de variables con fuga de información (`reservation_status`, `assigned_room_type`).
- Creación de nuevas variables (`total_guests`, `total_nights`, `is_long_stay`).
- Partición train/test respetando el orden cronológico de las reservas.
- Entrenamiento de cuatro modelos: Regresión Logística, Random Forest, Gradient Boosting y XGBoost.
- Gestión del desbalanceo de clases mediante ajuste de pesos.
- Optimización de hiperparámetros con Optuna sobre validación temporal.
- Interpretabilidad del modelo ganador con SHAP (summary plot y waterfall).

## 🏆 Modelo ganador

**XGBoost (balanceado)**, seleccionado por su mejor equilibrio entre precision y recall:

| Métrica | Valor |
|---|---|
| Accuracy | 0,8021 |
| Precision | 0,7478 |
| Recall | 0,7805 |
| F1-score | 0,7638 |
| ROC-AUC | 0,8931 |

## 📐 Variables más determinantes (SHAP)

1. Tipo de depósito no reembolsable
2. País de origen (Portugal)
3. Antelación de la reserva
4. Plazas de parking solicitadas (reduce el riesgo)
5. Número de peticiones especiales (reduce el riesgo)

## 💡 Principales insights

- El City Hotel cancela un 41,8 % de sus reservas frente a un 27,8 % del Resort Hotel.
- A mayor antelación de la reserva, mayor tasa de cancelación, pasando de un 9,6 % a más de un 67 %.
- El canal de agencias y touroperadores cancela mucho más que el canal directo.
- El depósito no reembolsable, contra lo esperable, se asocia a mayor riesgo de cancelación.

## 🚨 Sistema de aviso propuesto

A partir del modelo ganador se ha construido un sistema que clasifica cada reserva en riesgo alto (26,6 %), medio (16,2 %) o bajo (57,2 %), asignando una acción preventiva a cada nivel. El ingreso estimado en riesgo por cancelaciones no evitadas en el grupo de riesgo alto asciende a **2.840.390,44 €**.

## 📚 Habilidades demostradas

Este proyecto demuestra experiencia práctica en:

- Limpieza y transformación de datos
- Ingeniería de variables
- Modelado predictivo y comparación de algoritmos
- Gestión del desbalanceo de clases
- Optimización de hiperparámetros
- Interpretabilidad de modelos (SHAP)
- Traducción de un modelo técnico en una propuesta de negocio
- Comunicación de resultados orientada a negocio

## 👩‍💻 Autora

**Marta Parás Gutiérrez**

Telecommunications Engineer | Data Analyst | Data Science & AI

[GitHub](https://github.com/Marta-Paras-Gutierrez)
