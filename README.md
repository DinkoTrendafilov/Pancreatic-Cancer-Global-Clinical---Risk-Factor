# Pancreatic Cancer Prognostic Pipeline

## Overview
This repository contains an end-to-end clinical analytics framework for **Pancreatic Ductal Adenocarcinoma (PDAC)** prognosis. The project bridges traditional biostatistical survival analysis with modern machine learning to provide high-recall risk stratification for clinical decision support.

## Project Structure
The analysis is modularized into distinct phases to ensure reproducibility and statistical rigor:
1.  **Data Engineering:** Cleaning and stratification of global clinical datasets.
2.  **Survival Analysis:** Non-parametric (Kaplan-Meier, Log-Rank) estimation of survival trajectories.
3.  **Hazard Modeling:** Semi-parametric Cox Proportional Hazards for multivariate risk quantification.
4.  **Predictive Modeling:** Machine Learning (XGBoost, Random Forest) pipeline optimized for high-recall clinical alerts.

## Key Technical Features
* **MLOps Integration:** Uses **MLflow** for programmatic experiment tracking, parameter logging, and artifact registry.
* **Clinical Optimization:** Custom cost-sensitive weighting to prioritize **Recall** (ensuring no high-risk patients are missed) while maintaining an **F1-Score > 0.90**.
* **Clinical Utility:** The pipeline includes a real-time simulation module for processing new patient data and generating automated risk alerts.

## Methodology
This pipeline follows a scientific approach, moving from univariate statistical screening to multivariate predictive modeling. It addresses common clinical data challenges such as censoring, multicollinearity, and class imbalance.

## Tech Stack
* **Languages:** Python
* **ML/Stats:** `scikit-learn`, `xgboost`, `lifelines`, `pandas`, `numpy`
* **MLOps:** `MLflow`
* **Visualization:** `matplotlib`, `seaborn`

## Clinical Significance
By identifying prognostic drivers earlier and with higher precision, this framework assists oncologists in tailoring therapeutic strategies, moving closer to data-driven, precision oncology.

---
*Course Final Exam Project | June 2026*