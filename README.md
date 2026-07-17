# Optimizing Oncology Resource Allocation: 10-Year Global Patient Cohort Analysis

---

## 🎯 Executive Summary & Business Impact
This repository contains a full-stack data strategy sandbox and predictive machine learning pipeline built to evaluate a longitudinal cohort of **50,000 global cancer patient records (2015-2024)**. 

### 📈 Core Business Insight & Recommendations
*   **The Problem:** Hospital networks traditionally distribute oncology budgets based on crude metrics like chronological age or linear staging models.
*   **The Discovery:** This multi-variable analysis proves that age distribution remains flat ($20 \le \text{Age} \le 90$) across all severity indices. Instead, continuous `Treatment_Cost_USD` variance is heavily driven by compound interactions between non-linear metabolic risk indices (`Obesity_Level`) and `Genetic_Risk`.
*   **Operational Takeaway:** Healthcare administrators should pivot resource allocation away from age-monopolized preventative frameworks, reallocating budget channels toward early target screening infrastructure in high-metabolic/genetic-risk zones to optimize financial lifecycle exposure.

---

## 🏗️ Technical Architecture & Pipeline Strategy

The pipeline scales across qualitative classification architectures for risk mapping and continuous regression architectures for expenditure forecasting:
[ Data Ingestion & Quality QA ] ──► [ Label Encoding (Qualitative Vectors) ]
│
[ Stratified Train/Test Split ]
│
┌─────────────────────────────────┴─────────────────────────────────┐
▼                                                                   ▼
[ Classification Sub-Engine ]                                      [ Continuous Regression Sub-Engine ]
(Target: Severity Score Mapping)                                   (Target: Treatment Cost Forecasts)
├── Baseline: Gaussian Naive Bayes                                 ├── Baseline: Ordinary Least Squares (OLS)
└── Ensemble: Random Forest Classifier                             └── Ensemble: Random Forest Regressor
---

## 📊 Feature Taxonomy Matrix

| Category | Feature Name | Data Type | Operational Description |
| :--- | :--- | :--- | :--- |
| **Demographics** | `Age` | Continuous | Patient age at initial clinical evaluation profile. |
| **Demographics** | `Gender` | Categorical | Demographic distribution control mapping (`Male`/`Female`/`Other`). |
| **Clinical Vector**| `Country_Region` | Categorical | Geographic distribution control vector mapping across global boundaries. |
| **Clinical Vector**| `Cancer_Type` | Nominal | Primary diagnostic oncological site alignment. |
| **Clinical Vector**| `Cancer_Stage` | Ordinal | Pathological staging tier bounds (`Stage 0` to `Stage IV`). |
| **Metrics / Targets**| `Treatment_Cost_USD` | Continuous | Direct financial expenditure incurred during therapeutic lifecycle. |
| **Metrics / Targets**| `Target_Severity_Score`| Continuous | Composite score indexing overall case complexity matrix bounds. |

---
💻 System Deployment & Replication

To replicate this diagnostic pipeline and run the machine learning notebook locally, execute the following commands in your terminal environment:

# Clone the repository asset
git clone [https://github.com/anmolrawat626/global-cancer-risk-analysis.git](https://github.com/anmolrawat626/global-cancer-risk-analysis.git)
cd global-cancer-risk-analysis

# Initialize environment dependencies
pip install -r requirements.txt
