
# IMDB Data Analytics Project

Proyecto de Data Analytics enfocado al análisis de rentabilidad en la industria cinematográfica utilizando datos de IMDB.

El proyecto cubre todo el ciclo de un análisis de datos: adquisición, limpieza, transformación, análisis exploratorio y visualización mediante un dashboard interactivo en Power BI.


## Objetivo del Proyecto

 Analizar la relación de los siguientes guiones, con el fin de identificar patrones de negocio y apoyar la toma de decisiones estratégicas en la industria del entretenimiento:

 - Presupuesto

 - Ingresos

 - Rentabilidad (ROI)

 - Género cinematográfico

 - Percepción del público (sentimiento de reviews)


## Estructura del Proyecto

```
imdb-data-analytics-project/
│
├── data/
│   ├── raw/
│   │   ├── IMDB Dataset.csv
│   │   └── imdb_movies.csv
│   │
│   └── processed/
│       ├── imdb_movies_clean.csv
│       ├── imdb_reviews_clean.csv
│       ├── imdb_final_dataset.csv
│       ├── final_dataset.csv
│       └── final_dataset_powerbi.csv
│
├── docs/
│   ├── INFORME EXPLICATIVO.odt
│   └── INFORME EXPLICATIVO.pdf
│
├── notebooks/
│   └── 01_exploracion_inicial.ipynb
│
├── visualization/
│   └── POWER BI - DASHBOARD DATASET FINAL.pbix
│
├── .gitignore
└── README.md
```

## Descripción de los Datasets
### Dataset A – Películas (imdb_movies.csv)

Incluye información estructural y financiera:

 - Título

 - Género

 - Fecha de estreno

 - Presupuesto

 - Ingresos

 - País

 - Idioma original

 - Puntuación media

### Dataset B – Reviews (IMDB Dataset.csv)

Incluye:

 - Texto de la reseña

 - Clasificación de sentimiento (positive / negative)


## Pipeline de Datos

El proyecto sigue las siguientes fases:

**1) Carga y Exploración**

 - Revisión de estructura

 - Análisis de tipos de datos

 - Detección de valores nulos

 - Eliminación de duplicados

**2) Limpieza y Transformación**

 - Normalización de columnas financieras

 - Conversión de fechas

 - Eliminación de registros inconsistentes

 - Los datasets limpios se almacenan en:
 
``` 
/data/processed
```
**3) Enriquecimiento de Datos**

Dado que no existe una clave directa entre películas y reviews, se implementa una estrategia de agregación:

 - Cálculo del porcentaje global de reviews positivas y negativas

 - Incorporación de métricas agregadas al dataset principal

**4) Creación de Métricas de Negocio**

Se generan nuevas variables clave:

*Beneficio = Revenue - Budget*

*ROI = (Revenue - Budget) / Budget*

Estas métricas permiten evaluar la rentabilidad real de cada película.

## Análisis Exploratorio (EDA)

Se estudian:

 - Distribución de presupuestos

 - Distribución de ingresos

 - Relación Presupuesto vs Ingresos

 - Rentabilidad por género

 - Identificación de outliers

 - Ranking de películas más rentables

Hallazgo principal:

 - **Un mayor presupuesto no garantiza una mayor rentabilidad.**


## Dashboard en Power BI

El archivo del dashboard se encuentra en:
``` 
visualization/POWER BI - DASHBOARD DATASET FINAL.pbix
```
El dashboard permite realizar análisis dinámicos orientados a la toma de decisiones empresariales e incluye:

#### KPIs

 - **Ingresos totales**

 - **Presupuesto total**

 - **Beneficio total**

 - **ROI**

#### Visualizaciones

 - **Dispersión Presupuesto vs Ingresos**

 - **Rentabilidad media por género**

 - **Ranking Top películas por ROI / Top 20**

 - **Tabla interactiva de resultados**

#### Filtros interactivos

 - **Género**

 - **Fecha de estreno**

 - **Presupuesto**


## Conclusiones Empresariales

1. **El ROI es una métrica más relevante que los ingresos absolutos.**

2. **Las producciones de presupuesto medio presentan un mejor equilibrio riesgo-retorno.**

3. **Existen diferencias claras de rentabilidad entre géneros.**

4. **El análisis de datos permite optimizar decisiones de inversión y asignación de capital.**


## Ejecución Local
 *1º Clonar el repositorio*
 ```
git clone https://github.com/RaulEcija/imdb-data-analytics-project.git
cd imdb-data-analytics-project
``` 

 *2º Ejecutar el análisis en Python*

 - Abrir el notebook:
``` 
notebooks/01_exploracion_inicial.ipynb
```

 - Ejecutar todas las celdas para reproducir el proceso de limpieza y análisis.

**(Requisitos)** :
```
pip install pandas numpy matplotlib seaborn
```

 *3º Abrir el Dashboard*

 - Abrir Power BI Desktop

 - Cargar el archivo:
```
visualization/POWER BI - DASHBOARD DATASET FINAL.pbix
```

## Limitaciones

 - No existe clave directa entre películas y reviews

 - Análisis de sentimiento binario (positive / negative)

 - No se implementan modelos predictivos

## Posibles Mejoras Futuras

*Modelos predictivos de éxito comercial*

*Análisis temporal de tendencias*

*Análisis más avanzado sobre reviews*

*Integración con datos adicionales (premios, ratings detallados, etc.)*

## Autor

**Raúl Écija Maeso**

