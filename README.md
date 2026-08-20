# Análisis de clientes y uso de servicios — ConnectaTel

## 📊 Descripción del proyecto

Este proyecto analiza el comportamiento de los clientes de **ConnectaTel**, una empresa de telecomunicaciones con operaciones en Latinoamérica.

El objetivo es comprender cómo los clientes utilizan los servicios de llamadas y mensajes, identificar comportamientos atípicos, segmentar usuarios y obtener conclusiones que puedan ayudar a mejorar la oferta comercial y la experiencia del cliente.

## 🎯 Objetivos

* Explorar y limpiar diferentes fuentes de datos.
* Identificar valores nulos, inválidos y sentinels.
* Estandarizar los datos y las fechas.
* Integrar información de clientes, planes y uso.
* Obtener estadísticas de uso por cliente.
* Identificar valores atípicos mediante visualizaciones y el método IQR.
* Crear segmentos de clientes según su comportamiento de uso y edad.
* Generar recomendaciones comerciales basadas en los resultados.

## 📁 Datasets utilizados

El análisis utiliza tres fuentes principales:

* `plans.csv`: información de los planes, incluyendo precio mensual, minutos, mensajes, GB y costos adicionales.
* `users_latam.csv`: información de los clientes, incluyendo edad, ciudad, fecha de registro, plan y churn.
* `usage.csv`: registros de utilización de llamadas y mensajes.

Los datos corresponden al periodo de análisis considerado en el proyecto, con información registrada hasta 2024.

## 🔎 Etapas del análisis

### 1. Carga y exploración

Se cargaron los tres datasets utilizando Pandas y se revisaron:

* primeras filas;
* dimensiones;
* tipos de datos;
* valores no nulos;
* estructura general de las tablas.

### 2. Calidad de los datos

Se analizaron:

* valores nulos;
* valores inválidos;
* sentinels;
* variables categóricas;
* identificadores;
* fechas fuera de rango.

Entre los problemas detectados se encontraron valores faltantes en algunas columnas y registros que requerían tratamiento antes del análisis.

### 3. Limpieza

Se aplicaron reglas de limpieza para:

* reemplazar el sentinel `-999` en `age`;
* convertir `?` en `city` a valores nulos;
* identificar y marcar fechas futuras como valores nulos;
* conservar como nulos los valores de `duration` y `length` cuando correspondían a tipos de registro donde estas variables no aplicaban.

### 4. Análisis de uso

Se construyó un perfil de uso por usuario con métricas como:

* cantidad de mensajes;
* cantidad de llamadas;
* minutos totales de llamadas.

Posteriormente, esta información se combinó con los datos de los usuarios.

### 5. Visualización y outliers

Se utilizaron histogramas y boxplots para analizar:

* edad;
* cantidad de mensajes;
* cantidad de llamadas;
* minutos de llamadas.

También se utilizó el método IQR para identificar valores extremos y evaluar su posible impacto en el análisis.

### 6. Segmentación

Se crearon dos tipos principales de segmentos:

**Segmentación por uso**

* Bajo uso
* Uso medio
* Alto uso

**Segmentación por edad**

* Joven
* Adulto
* Adulto Mayor

Estas categorías permiten analizar diferencias en el comportamiento de los clientes y detectar oportunidades comerciales.

## 💡 Resultados e insights

El análisis permitió identificar diferencias en los patrones de uso entre los clientes, así como valores extremos que requieren revisión desde una perspectiva de negocio.

Los segmentos creados permiten estudiar de manera diferenciada a los usuarios según su edad y nivel de consumo, facilitando la identificación de oportunidades para mejorar la oferta de servicios.

Los resultados detallados, gráficos y conclusiones se encuentran en el notebook del proyecto.

## 🛠️ Herramientas utilizadas

* Python
* Pandas
* NumPy
* Seaborn
* Matplotlib
* Jupyter Notebook
* GitHub

## ▶️ Cómo reproducir el análisis

1. Descargar o clonar este repositorio.
2. Abrir el archivo `S7_ConnectaTel_revisado_corregido.ipynb`.
3. Ejecutarlo utilizando Jupyter Notebook, JupyterLab o Google Colab.
4. Tener disponibles los tres datasets utilizados por el proyecto.
5. Ejecutar las celdas en orden para reproducir el análisis.

> Nota: las rutas de los archivos pueden variar dependiendo del entorno donde se ejecute el notebook. En el entorno original del proyecto se utilizaron las rutas proporcionadas por la plataforma.

## 📌 Archivo principal

`S7_ConnectaTel_revisado_corregido.ipynb`

Contiene el análisis completo, incluyendo exploración, limpieza, estadísticas, visualizaciones, detección de outliers y segmentación.

## 👤 Autor

**Jorge Ledesma**

Proyecto de análisis de datos realizado como parte del aprendizaje de Analista de Datos.
