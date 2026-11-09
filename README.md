# Movilidad Urbana y Economía en Latinoamérica – Análisis 2024

Este repositorio contiene el análisis que relaciona la **congestión de tráfico** con **indicadores económicos** de ciudades latinoamericanas.

El análisis combina dos datasets: `tomtom_traffic.csv` (métricas de tráfico de TomTom) y `oecd_city_economy.csv` (indicadores económicos de la OCDE). Cubren ciudades de Argentina, Brasil, Chile, Colombia, México, Perú y Uruguay, con datos de 2023 a 2025. El análisis se centra en **2024**.

## 📂 Contenido del repositorio

- `S5_ladb_mobility_economy_project_student_(1).ipynb`
  → Notebook principal con exploración, limpieza, unión de datasets, visualizaciones y conclusiones.

## ▶ Cómo abrir el notebook en Google Colab

Haz clic en el siguiente botón:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1Uh_QLZNSdI8ctBpLfygUk93DoB-hItlS)

O:

1. Abre el archivo `.ipynb` en GitHub
2. Haz clic en **Open in Colab**

## 📘 Cómo reproducir el análisis

1. Abre el notebook `S5_ladb_mobility_economy_project_student_(1).ipynb`
2. Asegúrate de tener disponibles los archivos `tomtom_traffic.csv` y `oecd_city_economy.csv` en la ruta que usa el notebook (`/datasets/`), o ajusta la ruta
3. Ejecuta las celdas en orden
4. Al final, el notebook exporta el dataset limpio como `ladb_mobility_economy_2024_clean.csv`

## 🛠 Proceso del análisis

1. **Exploración inicial:** revisión de la estructura y contenido de ambos datasets (`head()`, `info()`).
2. **Limpieza y preparación:**
   - Estandarización de nombres de columnas a formato `snake_case`.
   - Conversión de columnas de tráfico a tipo fecha (`pd.to_datetime`).
   - Limpieza de separadores y símbolos (`%`, puntos y comas) para convertir a numérico el PIB per cápita, el desempleo y la población.
   - Cálculo de la población en unidades absolutas.
   - Extracción del año y filtrado de 2024.
3. **Agregación:** promedio de las métricas de tráfico por ciudad, país y año.
4. **Unión de datasets:** `merge` tipo *inner* por ciudad y año.
5. **Visualización:** boxplot de `jams_delay`, histograma del PIB per cápita y gráfico de barras que compara el retraso por tráfico con el PIB per cápita por ciudad.

## 🧠 Objetivo del análisis

- Preparar y unir datos de tráfico y economía urbana
- Explorar distribuciones y detectar valores atípicos
- Evaluar si existe relación entre el PIB per cápita y la congestión
- Generar insights para orientar decisiones de inversión en movilidad por ciudad

## 📊 Principales hallazgos

- **No se observa una relación clara** entre el PIB per cápita y el nivel de congestión (`jams_delay`).
- **Montevideo** tiene el mayor PIB per cápita y, al mismo tiempo, el menor retraso en tráfico.
- **Ciudad de México** presenta el mayor retraso promedio por tráfico.
- **Santiago** muestra mayor proporcionalidad entre el retraso en tráfico y el PIB per cápita.
- Otros factores (infraestructura vial, calidad del transporte público, densidad poblacional) probablemente explican mejor la congestión y se recomienda analizarlos.

## 🧰 Tecnologías

Python · pandas · numpy · seaborn · matplotlib
