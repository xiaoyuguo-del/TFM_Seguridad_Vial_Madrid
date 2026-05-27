# TFM - Sistema de Priorización de Intervenciones en Seguridad Vial de Usuarios Vulnerables No Motorizados. Municipio De Madrid (2010-2026)

## Descripción

Este repositorio contiene los notebooks de Python desarrollados para el Trabajo Fin de Máster. El sistema combina un Índice de Prioridad Descriptivo (IPD) y un Índice de Riesgo Predictivo (IRP) para priorizar intervenciones de seguridad vial de peatones y ciclistas en los 21 distritos de Madrid.

## Notebooks

| Notebook | Descripción |
|---|---|
| 01_ETL_tabla_maestra | ETL principal 2019-2025: limpieza, deduplicación VRU, tablas maestras |
| 01b_ETL_2010-2018 | ETL histórico 2010-2018: armonización PEA, imputación COVID |
| 02_Indice_Descriptivo | Cálculo del IPD: normalización, ponderación, ranking |
| 02b_IPD_analisis_exploratorio | Análisis exploratorio y sensibilidad del IPD |
| 03_Modelos | Walk-Forward Validation, comparativa de modelos, Ridge final |
| 03b_Estadistica | Estadísticas descriptivas de acc_ponderado: media, desviación típica, varianza entre distritos y años, impacto COVID 2020 |
| 04_Prediccion_2026 | Predicción IRP 2026, score final |
| 05_Sensibilidad_Score | Análisis de sensibilidad del Score Final |
| 06_Analisis_Top3 | Análisis en profundidad Centro, Chamberí y Salamanca |
| 07_Preparacion_PowerBI | Generación de CSVs y GeoJSON para Power BI |

## Cómo ejecutar

1. Clona el repositorio o descarga los notebooks
2. Descarga los datos de las fuentes indicadas en la sección **Datos**
3. Crea la siguiente estructura de carpetas en tu Google Drive:

   TFM_Seguridad_Vial/

   ├── datos/

   │   ├── accidentes_general/raw/

   │   ├── accidentes_bici/raw/

   │   ├── poblacion_distrito/

   │   ├── distritos/raw/

   │   ├── infraestructura_ciclista/

   │   └── emt_paradas/

   └── outputs/


5. Abre cada notebook en Google Colab
6. Ajusta la variable `BASE` al inicio de cada notebook con tu ruta de Drive
7. Ejecuta los notebooks en orden numérico: 01 → 01b → 02 → 02b → 03 → 03b → 04 → 05 → 06 → 07
8. Los outputs se guardan automáticamente en `outputs/` dentro de tu Drive

> **Nota:** Los notebooks están diseñados para ejecutarse en Google Colab 
> con Google Drive. Para ejecutarlos localmente es necesario adaptar 
> las rutas de los ficheros definidas en la variable `BASE` al inicio 
> de cada notebook.


## Dependencias

Instala las dependencias con:

pip install -r requirements.txt


Los notebooks están desarrollados en Google Colab (Python 3.10).


## Datos

Los datos no están incluidos en el repositorio. Descárgalos manualmente desde las siguientes fuentes:

| Fuente | URL | Periodo |
|---|---|---|
| Accidentes de tráfico (SIGIT/PEA) | https://datos.madrid.es/dataset/300228-0-accidentes-trafico-detalle | 2010-2025 |
| Padrón Municipal | https://datos.madrid.es/dataset/300557-0-poblacion-distrito-barrio | 2019-2024 |
| Geoportal — distritos y red ciclista | https://geoportal.madrid.es | Estático |
| OpenStreetMap (via OSMnx) | https://www.openstreetmap.org | Estático |
| Estaciones BiciMAD (EMT Madrid) | https://datos.emtmadrid.es/dataset/5fcc0945-2cbd-46c3-801a-6a83f4167c11/resource/105ce5df-793f-4e0a-a88e-5d3b3f024a5d/download/bikestationbicimad_geojson.geojson | Estático |

Una vez descargados, colócalos en la carpeta `datos/` de tu Google Drive siguiendo la estructura definida al inicio de cada notebook.
