# trackeo_electoral

# Procesamiento y análisis de tracking lectoral

Este proyecto implementa una herramienta integral en Python para el procesamiento, imputación, ponderación y visualización de datos de encuestas electorales. El objetivo principal es transformar bases de datos crudas (CSV) en insights estratégicos, permitiendo corregir sesgos muestrales mediante técnicas estadísticas y explorar tendencias de voto a través de una interfaz interactiva.

## Descripción del flujo de trabajo

El script ejecuta una secuencia lineal de pasos diseñada para asegurar la consistencia de los datos antes de cualquier análisis. En primer lugar, se realiza una limpieza y normalización exhaustiva de las columnas, estandarizando nombres de variables críticas como fecha, sexo, edad y ubicación geográfica, además de detectar y eliminar registros inválidos que carezcan de información esencial.

Una vez depurada la base, el sistema maneja los datos faltantes utilizando algoritmos de aprendizaje automático. Se implementa un imputador iterativo (MICE) que utiliza las correlaciones entre el voto, el estrato social y otras variables demográficas para estimar valores ausentes en campos numéricos y categóricos, reduciendo la pérdida de información.

Posteriormente, se ofrece un módulo de ajuste poblacional o ponderación (raking). El usuario puede elegir equilibrar la muestra según parámetros censales reales, como sexo, rango etario, nivel educativo o distribución geográfica, para corregir la representatividad de la encuesta.

Finalmente, el script entrena un modelo de regresión logística para identificar qué variables impactan más en la decisión de voto por un candidato específico y despliega un menú interactivo de visualización. Este menú permite generar histogramas, gráficos de dispersión, análisis de tendencias temporales y mapas de calor sobre la cartografía de Argentina.

## Requisitos y configuración

Para ejecutar este software es necesario contar con un entorno de Python 3 que incluya las librerías pandas, numpy, matplotlib, geopandas y scikit-learn. Además, el script espera encontrar en el directorio de trabajo el archivo cartográfico "provincias.json" del Instituto Geográfico Nacional para la generación de mapas, así como los archivos CSV de referencia censal si se desea utilizar la función de ponderación.

## Guía de uso

Al iniciar el programa desde la terminal, se solicitará el nombre del archivo CSV que contiene la encuesta. El sistema procesará automáticamente la limpieza y la imputación de datos. A continuación, se presentará una serie de menús interactivos donde se deberá seleccionar el método de ponderación deseado y el candidato objetivo para el análisis predictivo.

Tras completar el procesamiento, el script guardará automáticamente una versión procesada de la base de datos y archivos de seguimiento (tracking) en carpetas locales. El usuario permanecerá en un bucle de visualización donde podrá explorar diferentes gráficos estadísticos o mapas territoriales hasta que decida finalizar la sesión.

## Autoría

Desarrollado como herramienta de soporte para análisis político y metodología de opinión pública, integrando técnicas de ciencia de datos con investigación social empírica.
