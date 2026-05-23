# TFM - Sistema de Priorización de Intervenciones en Seguridad Vial de Usuarios Vulnerables No Motorizados. Municipio De Madrid (2010-2026)

**Descripción**

Este repositorio contiene los notebooks de Python desarrollados para el Trabajo Fin de Máster. El sistema combina un Índice de Prioridad Descriptivo (IPD) y un Índice de Riesgo Predictivo (IRP) para priorizar intervenciones de seguridad vial de peatones y ciclistas en los 21 distritos de Madrid.

**Notebooks**

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

**Datos**

Los datos utilizados provienen de fuentes públicas del Ayuntamiento de Madrid y están disponibles en el Portal de Datos Abiertos: https://datos.madrid.es
