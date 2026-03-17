# Predictive People Analytics with Neural Networks (RNA)

## 📋 Project Overview

This project implements a **full end-to-end machine learning pipeline** for predicting workforce hiring and attrition events using **Artificial Neural Networks (ANN)**. The system is designed to generate quarterly headcount movement forecasts and their associated cost projections, delivering actionable intelligence for strategic HR planning.

The pipeline covers the complete data science lifecycle — from synthetic data generation to executive dashboard creation — demonstrating production-grade data engineering and ML capabilities applied to the People Analytics domain.

> **⚠️ IMPORTANT**: Before using or interpreting model outputs, please read [`ReadMe_SupuestosModelo.md`](./ReadMe_SupuestosModelo.md) for a full description of model assumptions, limitations, and technical constraints.

---

## 🚀 Technology Stack

### 💻 Development Environment
- **Google Colab Notebook**: Cloud-based platform for pipeline development and execution

### 🐍 Programming Language
- **Python 3.x**: Primary language across the full stack

### 📚 Libraries & Frameworks

#### Machine Learning & Data Processing
| Library | Role |
|---|---|
| **TensorFlow / Keras** | Neural network architecture, training, and inference |
| **scikit-learn** | Data preprocessing, feature encoding, and evaluation metrics |
| **pandas** | Tabular data manipulation and aggregation |
| **NumPy** | Numerical operations and array computations |

#### Visualization
| Library | Role |
|---|---|
| **matplotlib** | Static charts and model performance plots |
| **seaborn** | Statistical visualizations, heatmaps, and distribution plots |

#### Utilities & Persistence
| Library | Role |
|---|---|
| **joblib** | Model and transformer serialization |
| **openpyxl** | Excel report generation |
| **IPython.display** | Enhanced notebook output rendering |

---

## 🔧 Pipeline Architecture

The pipeline is structured into **7 sequential stages**:

```
Stage 1 → Synthetic Data Generation
Stage 2 → Preprocessing & ANN Training
Stage 3 → Model Performance Visualization
Stage 4 → Future Forecast (4 quarters)
Stage 5 → Forecast Dashboard
Stage 6 → Budget Projection
Stage 7 → Executive Summary Report
```

| Stage | Description |
|---|---|
| **1 — Synthetic Data Generation** | Creates a statistically realistic dataset using configurable probability distributions |
| **2 — Preprocessing & ANN Training** | Trains two independent models: one for hires, one for attrition |
| **3 — Model Performance Visualization** | Evaluates model accuracy with residual plots and error metrics |
| **4 — Future Forecast** | Generates predictions for the next 4 fiscal quarters |
| **5 — Forecast Visualization** | Interactive dashboards displaying headcount projections by project and area |
| **6 — Budget Generation** | Converts headcount predictions into financial cost estimates |
| **7 — Executive Summary** | Formatted tables ready for C-level and HR leadership presentations |

---

## 📊 Key Features

- **Dual Independent Models**: Separate ANNs for hires and attrition events, avoiding target leakage
- **Configurable Architectures**: 4 selectable network complexity profiles to fit different data volumes
- **Confidence Intervals**: Range estimates derived from historical model error, enabling uncertainty quantification
- **Realistic Cost Factors**: Industry-calibrated multipliers (3.2× hires, 1.5× attrition) for budget accuracy
- **Comprehensive Visualizations**: Heatmaps, histograms, trend lines, and executive summary tables
- **Business-Ready Output**: Excel reports and formatted tables suitable for direct stakeholder delivery

---

## 🎯 Use Cases

| Use Case | Description |
|---|---|
| **Workforce Planning** | Anticipate quarterly hiring needs by project and area |
| **Budget Management** | Estimate personnel costs for financial planning cycles |
| **Attrition Analysis** | Identify organizational units with elevated turnover probability |
| **Strategic Decision-Making** | Provide quantitative evidence for HR and executive strategy |

---

## 📁 Repository Structure

```
Predictive_People_Analythics_with_RNA/
├── README.md                       # This file — project overview (English)
├── ReadMe_SupuestosModelo.md       # Model assumptions & constraints (English)
├── Pipeline_Diagrama.png           # Visual diagram of the pipeline stages
├── requirements.txt                # Python dependency manifest
├── notebooks/                      # Google Colab source notebooks
│   └── *.ipynb
├── data/                           # Generated datasets (auto-created at runtime)
│   ├── dataset_contrataciones.csv  # Synthetic hiring/attrition dataset
│   ├── forecast_rrhh.csv           # Model forecast output
│   └── presupuesto_rrhh.xlsx       # Budget projection report (Excel)
├── models/                         # Serialized trained ANN models (.keras / .h5)
├── scalers/                        # Persisted feature scalers (joblib)
└── encoders/                       # Persisted label encoders (joblib)
```

> **Google Colab note**: The `data/`, `models/`, `scalers/`, and `encoders/` directories are created automatically at pipeline runtime. No manual directory setup is required.

---

## ⚡ Quick Start

1. Open the main notebook in Google Colab.
2. Execute pipeline stages sequentially from **Stage 1** through **Stage 7**.
3. Review the metrics and visualizations rendered inline.
4. Download or inspect the generated output files (`.csv` / `.xlsx`).

---

## 📈 Evaluation Metrics

| Metric | Description |
|---|---|
| **MAE** (Mean Absolute Error) | Average absolute deviation in headcount predictions |
| **RMSE** (Root Mean Squared Error) | Error metric that penalizes large deviations more heavily |
| **R²** (Coefficient of Determination) | Proportion of target variance explained by the model |

---

## 🛠️ Local Development Setup

> **Compatibility note**: TensorFlow requires Python **3.9–3.12**. If running Python 3.13+, use Google Colab for model execution or create a compatible virtual environment.

```bash
# 1. Clone the repository
git clone https://github.com/Merlin2098/Predictive_People_Analythics_with_RNA.git
cd Predictive_People_Analythics_with_RNA

# 2. Create and activate a virtual environment (Python 3.10 recommended)
python -m venv .venv
.venv\Scripts\activate          # Windows
# source .venv/bin/activate     # macOS/Linux

# 3. Install dependencies
pip install -r requirements.txt

# 4. Launch the notebook
jupyter notebook notebooks/
```

---

**Project Version**: 1.0
**Last Updated**: September 2025
**Status**: Demonstrative / Academic
**Domain**: People Analytics · Workforce Forecasting · HR Data Engineering