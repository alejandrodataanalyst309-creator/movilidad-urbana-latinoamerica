Análisis de Movilidad Urbana y Desempeño Económico en Ciudades Latinoamericanas (2024)

📌 Descripción del proyecto

Este proyecto explora la relación entre la movilidad urbana y los indicadores económicos de diferentes ciudades latinoamericanas durante el año 2024.

A partir de datos del TomTom Traffic Index y OECD Cities, se analizan indicadores de congestión vehicular, tiempos de desplazamiento y retrasos en el tráfico, junto con variables económicas y demográficas, como el PIB per cápita, el desempleo y la población.

El propósito es transformar e integrar diferentes fuentes de datos para identificar patrones que contribuyan a comprender la relación entre el desempeño económico de las ciudades y sus condiciones de movilidad.

🎯 Objetivos

Analizar los niveles de congestión vehicular y los tiempos de desplazamiento entre ciudades.

Explorar la relación entre los retrasos del tráfico y el PIB per cápita.

Limpiar, estandarizar e integrar conjuntos de datos de movilidad y economía.

Identificar distribuciones, valores atípicos y posibles patrones en los indicadores de movilidad urbana.

Generar un conjunto de datos consolidado que facilite futuros análisis.

📊 Fuentes de datos

El proyecto utiliza dos fuentes principales:

Fuente

Descripción

TomTom Traffic Index

Información sobre congestión vehicular, retrasos, índices de tráfico y tiempos de desplazamiento.

OECD Cities

Indicadores económicos, demográficos y urbanos, incluidos el PIB per cápita, el desempleo, la población y PM2.5.

Periodo de análisis: 2024.

Los archivos de entrada utilizados por el notebook son:

/datasets/tomtom_traffic.csv

/datasets/oecd_city_economy.csv

Nota: los archivos originales deben estar disponibles en el entorno de ejecución. Si no se incluyen en el repositorio, será necesario obtenerlos de sus fuentes correspondientes.

🛠️ Herramientas y tecnologías

Python: lenguaje utilizado para el análisis de datos.

Pandas: limpieza, transformación, agrupación e integración de datos.

NumPy: operaciones numéricas.

Matplotlib: creación de visualizaciones.

Seaborn: visualización y análisis exploratorio.

Jupyter Notebook: desarrollo y documentación del análisis.

🔍 Metodología

El análisis se desarrolla mediante las siguientes etapas:

Carga y exploración de los datos
Se cargan los archivos CSV y se examinan su estructura, columnas, tipos de datos y posibles inconsistencias.

Limpieza y transformación
Se estandarizan los nombres de las columnas mediante el formato snake_case, se convierten las fechas al formato datetime y se transforman las variables económicas y demográficas a tipos numéricos.

Filtrado temporal
Se extrae el año de las fechas de los registros de tráfico y se seleccionan los datos correspondientes a 2024.

Agregación de indicadores de movilidad
Se agrupan los registros por ciudad, país y año para calcular métricas promedio de tráfico y obtener una visión consolidada de las condiciones de movilidad.

Integración de las fuentes
Se combinan los indicadores de movilidad con los datos económicos mediante un INNER JOIN, utilizando la ciudad y el año como criterios de integración.

Esta operación conserva únicamente las observaciones que tienen coincidencias en ambas fuentes.

Análisis exploratorio de datos
Se utilizan histogramas, diagramas de caja y gráficos de barras para estudiar la distribución de las variables, identificar valores atípicos y explorar posibles relaciones entre la congestión vehicular y los indicadores económicos.

Exportación de los resultados
Finalmente, se exporta el conjunto de datos integrado y procesado a un archivo CSV para facilitar su reutilización en otros análisis.

📈 Variables principales

Variable

Descripción

jams_delay

Indicador de retraso asociado a la congestión vehicular.

traffic_index_live

Índice de tráfico en tiempo real.

jams_length_kms

Longitud de los atascos en kilómetros.

jams_count

Número de atascos registrados.

mins_delay

Retraso expresado en minutos.

travel_time_live_per_10kms_mins

Tiempo de desplazamiento en tiempo real por cada 10 km, en minutos.

travel_time_hist_per_10kms_mins

Tiempo histórico de desplazamiento por cada 10 km, en minutos.

city_gdp_capita

PIB per cápita de la ciudad.

unemployment_pct

Indicador porcentual de desempleo.

pm25

Indicador relacionado con la concentración de partículas finas PM2.5.

population_m

Variable poblacional transformada durante el procesamiento.

💡 Hallazgos preliminares

El análisis exploratorio permite plantear preguntas sobre la relación entre el nivel de desarrollo económico y la congestión vehicular.

La interpretación inicial del notebook sugiere que un mayor PIB per cápita no necesariamente implica una mayor congestión, y que algunas ciudades con niveles de ingreso moderados o bajos también pueden experimentar retrasos importantes en el tráfico.

Estos patrones deben interpretarse como observaciones exploratorias. Las visualizaciones, por sí solas, no permiten establecer causalidad ni confirmar la existencia de relaciones estadísticamente significativas.

Para profundizar en los resultados, sería conveniente calcular coeficientes de correlación y desarrollar modelos estadísticos que permitan evaluar estas relaciones de manera más rigurosa.

📁 Estructura del proyecto

Se propone organizar el repositorio de la siguiente manera:

urban-mobility-economy/ │ ├── notebooks/ │ └── ladb_mobility_economy_project_student.ipynb │ ├── data/ │ └── README.md │ ├── outputs/ │ └── ladb_mobility_economy_2024_clean.csv │ ├── README.md └── requirements.txt

notebooks/: contiene el notebook con el análisis.

data/: incluye instrucciones para obtener los datos originales.

outputs/: almacena los resultados procesados.

README.md: documenta el proyecto.

requirements.txt: especifica las bibliotecas necesarias para ejecutar el análisis.

Esta estructura es una propuesta de organización; los directorios y archivos deben crearse según la configuración final del repositorio.

🚀 Instalación y ejecución

Requisitos previos

Python 3.10 o una versión compatible.

Jupyter Notebook o JupyterLab.

Acceso a los archivos de datos originales.

Clonar el repositorio
git clone cd urban-mobility-economy

Instalar las dependencias
pip install pandas numpy matplotlib seaborn jupyter

Preparar los datos
Ubica los archivos CSV en el directorio esperado por el notebook o modifica las rutas de lectura para que coincidan con su ubicación local.

Ejecutar el notebook
Inicia Jupyter Notebook:

jupyter notebook

Abre el archivo ladb_mobility_economy_project_student.ipynb y ejecuta las celdas en orden.

Revisar y exportar los resultados
Examina las visualizaciones generadas y verifica el conjunto de datos procesado al finalizar la ejecución.

📦 Resultado esperado

El notebook genera el siguiente archivo de salida:

ladb_mobility_economy_2024_clean.csv

Este archivo contiene los indicadores de movilidad y economía integrados para las observaciones de ciudad y año que coinciden en ambas fuentes durante 2024.

⚠️ Limitaciones

El análisis se concentra en un solo año y no permite identificar tendencias de largo plazo.

La integración mediante INNER JOIN excluye las observaciones sin coincidencias entre las fuentes.

Las diferencias en cobertura, definiciones y métodos de medición pueden afectar la comparabilidad entre ciudades.

Las asociaciones observadas no implican necesariamente relaciones de causalidad.

La reproducción del análisis depende de la disponibilidad y calidad de los datos originales.

🔮 Posibles mejoras

Calcular correlaciones de Pearson y Spearman entre los indicadores de movilidad y economía.

Desarrollar modelos de regresión para estudiar posibles relaciones entre las variables.

Incorporar datos de varios años para analizar la evolución de la congestión urbana.

Mejorar las visualizaciones mediante escalas comparables y análisis por ciudad y país.

Implementar validaciones automáticas para comprobar la calidad de los datos.

Crear un dashboard interactivo que permita explorar los resultados.

👤 Autor: Alejandro Valencia Lopez

[Tu nombre]

Proyecto de análisis de datos | Movilidad urbana | Indicadores económicos
