# Predictive People Analytics with RNA

## 📋 Resumen del Proyecto

Este proyecto implementa un **pipeline completo de machine learning** para la predicción de ingresos y ceses de personal utilizando **Redes Neuronales Artificiales (RNA)**. El sistema está diseñado para generar pronósticos de movimientos de personal y sus costos asociados a nivel trimestral, proporcionando información valiosa para la planificación estratégica de recursos humanos.

El pipeline incluye desde la generación de datos sintéticos hasta la creación de dashboards ejecutivos con presupuestos detallados, demostrando capacidades completas de ciencia de datos aplicada a People Analytics.

**⚠️ IMPORTANTE**: Para comprender las limitaciones, supuestos y consideraciones técnicas del modelo, consulte el documento [`ReadMe_SupuestosModelo.md`](./ReadMe_SupuestosModelo.md) antes de utilizar o interpretar los resultados.

## 🚀 Tecnologías Utilizadas

### 💻 Entorno de Desarrollo
- **Google Colab Notebook**: Plataforma cloud para desarrollo y ejecución del pipeline

### 🐍 Lenguaje de Programación
- **Python 3.x**: Lenguaje principal para todo el desarrollo

### 📚 Librerías y Frameworks

#### Machine Learning y Análisis de Datos
- **TensorFlow/Keras**: Construcción y entrenamiento de redes neuronales
- **scikit-learn**: Preprocesamiento de datos y métricas de evaluación
- **pandas**: Manipulación y análisis de datos estructurados
- **numpy**: Operaciones numéricas y arrays multidimensionales

#### Visualización
- **matplotlib**: Creación de gráficos y visualizaciones estáticas
- **seaborn**: Visualizaciones estadísticas avanzadas y heatmaps

#### Utilidades y Persistencia
- **joblib**: Serialización de modelos y transformadores
- **IPython.display**: Visualización mejorada en notebooks
- **os**: Operaciones del sistema operativo

#### Formato y Exportación
- **openpyxl**: Manipulación de archivos Excel

## 🔧 Arquitectura del Pipeline

El pipeline está estructurado en **7 pasos principales**:

1. **Generación de Datos Sintéticos**: Creación de dataset con distribuciones estadísticas realistas
2. **Preprocesamiento y Entrenamiento RNA**: Modelos especializados para ingresos y ceses
3. **Análisis Visual de Resultados**: Evaluación de precisión del modelo
4. **Forecast Futuro**: Predicciones para próximos 4 trimestres
5. **Visualización de Predicciones**: Dashboards interactivos de pronósticos
6. **Generación de Presupuesto**: Conversión de predicciones a costos financieros
7. **Resumen Ejecutivo**: Tablas de visualización para el presupuesto proyectado de HR

## 📊 Características Principales

- **Modelos Independientes**: RNA separadas para ingresos y ceses
- **Arquitecturas Configurables**: 4 opciones de complejidad de red neuronal
- **Rangos de Confianza**: Intervalos basados en error histórico del modelo
- **Factores de Costo Realistas**: 3.2x para ingresos, 1.5x para ceses
- **Visualizaciones Comprehensivas**: Heatmaps, histogramas y tablas resumen
- **Formato Empresarial**: Salidas listas para presentación ejecutiva

## 🎯 Casos de Uso

- **Planificación de RRHH**: Anticipar necesidades de contratación
- **Gestión de Presupuesto**: Estimar costos de personal por trimestre
- **Análisis de Rotación**: Identificar áreas con alta probabilidad de ceses
- **Toma de Decisiones**: Información cuantitativa para estrategia organizacional

## 📁 Estructura de Archivos

```
proyecto/
├── README.md                    # Este archivo
├── ReadMe_SupuestosModelo.md   # Limitaciones y supuestos técnicos
├── Pipeline_Diagrama.png        # Diagrama visual del pipeline
├── notebooks/                   # Notebooks de Google Colab
├── data/                        # Datasets generados
│   ├── dataset_contrataciones.csv
│   ├── forecast_rrhh.csv
│   └── presupuesto_rrhh.xlsx
├── models/                      # Modelos entrenados
├── scalers/                     # Transformadores persistidos
└── encoders/                    # Codificadores guardados
```

**Nota para Google Colab**: Todos los archivos de las carpetas (`data/`, `models/`, `scalers/`, `encoders/`) se generan automáticamente durante la ejecución del pipeline en el directorio de trabajo de Colab. No es necesario crear estas carpetas previamente.

## ⚡ Inicio Rápido

1. Abrir el notebook principal en Google Colab
2. Ejecutar los pasos del pipeline secuencialmente (Paso 1 → Paso Final)
3. Revisar las visualizaciones y métricas generadas
4. Analizar los archivos de salida (CSV/Excel)

## 📈 Métricas de Evaluación

- **MAE (Mean Absolute Error)**: Error promedio en número de personas
- **RMSE (Root Mean Square Error)**: Penalización de errores grandes
- **R² (Coeficiente de Determinación)**: Porcentaje de varianza explicada

---

**Versión del proyecto**: 1.0  
**Última actualización**: 09/2025  
**Estado**: Demostrativo/Académico