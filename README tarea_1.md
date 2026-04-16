# Tarea_1_censo
# Análisis Demográfico y Migratorio - Censo Chile 2024

Este repositorio contiene el código y los resultados del análisis de datos del Censo 2024 en Chile. El objetivo principal de este proyecto es explorar el perfil demográfico, educativo, laboral y los patrones migratorios de tres comunas específicas de la Región Metropolitana: **Conchalí, La Cisterna y Quinta Normal**.

## Descripción del Proyecto

El análisis se lleva a cabo mediante un Jupyter Notebook (`Tarea1_Censo2024-2.ipynb`) donde se extrae, limpia y cruza información de bases de datos de viviendas, hogares y personas en formato `.parquet`. A través de diversas visualizaciones y métricas, se logran identificar las principales diferencias y similitudes entre la población nacida en Chile y la población nacida en el extranjero residente en dichas comunas.

## Tecnologías y Librerías Utilizadas

El proyecto fue desarrollado en **Python 3** (Google Colab) y utiliza las siguientes librerías principales:
* `pandas` y `numpy` para la manipulación y análisis de datos estructurados.
* `matplotlib` para la creación de gráficos y visualizaciones.
* `pyarrow` para la lectura optimizada de archivos Parquet.
* `geopandas` y `mapclassify` para el manejo potencial de datos geoespaciales.

## Estructura del Análisis

El desarrollo del notebook está dividido en las siguientes secciones clave:

### 0. Carga de Datos y Joins
* Conexión con Google Drive y lectura de archivos `.parquet`.
* Filtrado de la población enfocada exclusivamente en los códigos comunales: `13104` (Conchalí), `13109` (La Cisterna) y `13126` (Quinta Normal).
* Fusión (Merge) de las tablas de personas, hogares y viviendas para obtener un dataset unificado.

### 1. Perfil Demográfico
* **Pirámide de Edad:** Comparación visual de la estructura de edad por sexo y origen (chilenos vs. extranjeros).
* **Ratio de Dependencia:** Cálculo de la población dependiente frente a la población en edad de trabajar (15 a 64 años).
* **Tamaño del Hogar:** Distribución de la cantidad de personas por hogar, segmentado por hogares exclusivamente chilenos frente a hogares con al menos un extranjero.
* **Educación y Empleo:** Comparación de los años de escolaridad promedio y las tasas de ocupación laboral según el lugar de nacimiento.

### 2. Pasaje Migratorio
* **Concentración de Extranjeros:** Porcentaje representativo de población migrante en cada una de las tres comunas.
* **Nacionalidades Frecuentes:** Top 10 de nacionalidades de los residentes nacidos fuera de Chile (ej. Venezuela, Perú, Colombia, etc.).
* **Movilidad Interna:** Análisis del lugar de residencia de las personas hace 5 años.
* **Periodos de Llegada:** Distribución del volumen de llegada de la población inmigrante segmentado en rangos de años (Ej: Antes de 2000, 2017-2021, 2022-2024).

## Conclusiones Principales

A partir de los datos analizados, se desprenden las siguientes conclusiones:
1. Las comunas de Conchalí, La Cisterna y Quinta Normal presentan una estructura demográfica caracterizada por una alta proporción de población en edad laboral y una presencia significativa de población migrante.
2. La población extranjera representa una fracción relevante del total, tendiendo a ser más joven y mostrando una mayor participación en el mercado laboral local.
3. La migración está altamente concentrada en individuos en edad activa y de llegada reciente.
4. Por otro lado, la población nacida en Chile presenta niveles de escolaridad promedio más altos.
5. Estos resultados evidencian la vital importancia de considerar la dimensión migratoria tanto en el análisis demográfico comunal como en el diseño de futuras políticas públicas.

## Cómo ejecutar el proyecto

1. Clona este repositorio:
   ```bash
   git clone [https://github.com/tu_usuario/nombre_del_repositorio.git](https://github.com/tu_usuario/nombre_del_repositorio.git)
