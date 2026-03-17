# ⚠️ Model Disclaimer & Assumptions

## 📋 Important Information for Pipeline Users

This document describes the **limitations, assumptions, and technical constraints** of the *Predictive People Analytics with Neural Networks* pipeline. Reading and understanding these points is essential before using or interpreting the model outputs in any context.

---

## 🚫 Data Limitations

### 📊 Fully Synthetic Dataset
All data used in this pipeline is **synthetically generated** and does not reflect information from any real organization. All values, patterns, and statistical relationships are the product of simulation algorithms and exist solely for demonstration purposes.

### 🎓 Academic & Demonstrative Purpose Only
This project is intended for **educational and technical showcase** purposes. Its goal is to demonstrate end-to-end ML pipeline development capabilities — **not** to deliver real-world business insights or production forecasts.

### ❌ Not Suitable for Real-World Decision-Making
The outputs — including predictions, forecasts, and budget estimates — **must not be applied in business environments** without prior validation against real organizational data, appropriate feature engineering, and domain expert review.

---

## 🏗️ Data Structure Assumptions

### 📋 Incomplete Historical Coverage
The dataset is **not an exhaustive record** of every (Project, Area, Quarter) combination across the four-year simulation window. It represents a **sparse and non-uniform sample** of operational data with irregular collection cadence — simulating real-world conditions where temporal gaps and missing periods are common in HR information systems.

### 🔍 Granularity Mismatch
The 1,500 records **simulate a real-world scenario** where data is originally collected at a finer grain than quarterly (e.g., monthly, weekly, or event-triggered), then aggregated upstream to the quarterly level for analysis. This structure reflects the typical complexity of enterprise information systems and ETL pipelines that feed analytical models.

### 🔄 Project Lifecycle Representation
For each project-area combination, the model uses the **most recently known state** as the basis for forward projections. This is implemented via `drop_duplicates(keep='last')`, a pragmatic approach that prioritizes the latest available information and avoids data leakage from future periods.

### 📐 Structured Forecast Grid
The pipeline generates a **uniform forecast lattice** of future data points — structured as 28 projects × 4 quarters = **112 forecast records** — based on unique historical entities. This design produces a consistent, predictable output format aligned with enterprise budget planning cycles.

---

## 📊 Data Generation Assumptions

### 🎲 Poisson Distribution — Headcount
Models **discrete personnel events** (employee count) using a fixed mean rate. This distribution is appropriate for positive integer counts that follow a specific frequency pattern, such as monthly hires or separations within an organizational unit.

### 📈 Normal Distribution — Costs & Hours
Applied to **continuous variables** that tend to cluster around a central mean with symmetric variance — a characteristic pattern for salary costs and worked hours within organizational contexts.

### 📏 Uniform Distribution — Workload
Assumes **equal probability** across the operational capacity range (from underutilization to overload), modeling scenarios where workload may vary uniformly between defined lower and upper bounds — a reasonable simplification in the absence of granular demand data.

### 🎯 Binomial Distribution — Hires & Attrition
Models **independent binary decisions** (hire / no-hire, separate / no-separate) for each employee, where each trial has a fixed and constant probability of success. This reflects the classic Bernoulli process underlying aggregate headcount movement.

---

## 🤖 Predictive Model Assumptions

### 💰 Cost Multipliers
| Event Type | Multiplier | Components Included |
|---|---|---|
| **Hires (Ingresos)** | **3.2×** | Full quarterly salary + recruitment fees + onboarding costs |
| **Attrition (Ceses)** | **1.5×** | Basic severance + social benefits + transition and knowledge-transfer costs |

> These multipliers are calibrated to approximate industry-standard HR cost structures. They should be recalibrated against actual organizational benchmarks before any real-world application.

### 📈 Constant Growth Rate
The model assumes a **5% quarter-over-quarter growth** in operational variables, simulating sustained organizational expansion. It does not account for recessionary cycles, hiring freezes, or non-linear growth patterns.

### 📊 Historical Pattern Persistence
The model operates under the fundamental assumption that **past trends continue into the forecast horizon**. No mechanism is included for detecting or adapting to structural breaks, market disruptions, or strategic pivots.

### 🔒 Exogenous Variables Treated as Static
**External economic conditions, regulatory changes, labor market shifts, and internal organizational restructurings** are held constant throughout the projection period and are not modeled as predictive features. This is a deliberate simplification for scope control in a demonstrative context.

### ⏭️ Annual Forecast Cycle
Forecasting is anchored to **fiscal year-end (Q4 close)**. Consequently, the four predicted quarters always correspond to the **following fiscal year**, providing a natural alignment with annual budget planning cycles.

---

## 🎯 Usage Recommendations

For teams considering this architecture as a reference implementation for production environments:

| Recommendation | Action |
|---|---|
| **Validate assumptions** | Audit whether model assumptions align with your organization's specific operational context and data characteristics |
| **Recalibrate parameters** | Adjust probability distributions, growth rates, and cost multipliers using real historical data from your organization |
| **Apply cross-validation** | Compare model predictions against held-out actuals to empirically assess predictive accuracy before deployment |
| **Establish model monitoring** | Schedule regular retraining cycles and implement drift detection to keep the model aligned with evolving workforce dynamics |

---

> This document is intended to promote responsible and informed use of ML-based forecasting tools in the People Analytics domain.
