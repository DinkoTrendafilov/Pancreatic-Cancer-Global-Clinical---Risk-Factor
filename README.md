# Pancreatic Cancer Prognostic Pipeline

## Overview
This repository provides an end-to-end clinical analytics framework designed for the prognosis of **Pancreatic Ductal Adenocarcinoma (PDAC)**. The project bridges traditional biostatistical survival analysis with modern machine learning, offering a robust solution for patient risk stratification. By integrating non-parametric survival estimators with high-recall predictive architectures, this pipeline serves as a scalable **Clinical Decision Support (CDS)** system.

## Project Structure & Methodology
The analysis is structured into a logical multi-phase pipeline to ensure statistical rigor and reproducibility:

1.  **Data Engineering & Cleaning:** Comprehensive preprocessing, handling missing data, and feature engineering to ensure input quality.
2.  **Non-Parametric Analysis:** Utilization of **Kaplan-Meier survival curves** and **Log-Rank tests** to visualize survival probabilities and compare clinical strata.
3.  **Hazard Modeling:** Implementation of **Multivariate Cox Proportional Hazards** models to quantify hazard ratios and identify statistically significant prognostic drivers.
4.  **Predictive Modeling (ML):** An advanced **XGBoost & Random Forest** pipeline designed to maximize clinical **Recall**, ensuring critical high-risk cases are identified with 100% sensitivity while maintaining an **F1-Score > 0.90**.

## Key Technical Features
* **MLOps Integration:** Centralized experiment tracking, parameter logging, and artifact registry via **MLflow**, enabling full auditability of every model iteration.
* **Clinical Optimization:** Implementation of cost-sensitive learning to address class imbalance, prioritizing the detection of non-surviving patient cohorts (Class 1).
* **Clinical Utility:** A built-in real-time simulation module that processes new, unseen patient intake data and outputs actionable clinical risk assessments.
* **Reproducibility:** All stochastic processes, including data sampling and model initialization, are strictly locked to `random_state=29` to guarantee consistent and verifiable results across all environments.

## Tech Stack
* **Core:** Python
* **Modeling:** `scikit-learn`, `xgboost`, `lifelines`
* **MLOps:** `MLflow`
* **Data Processing:** `pandas`, `numpy`
* **Visualization:** `matplotlib`, `seaborn`

## Clinical Significance
By identifying prognostic drivers earlier and with higher precision, this framework assists oncologists in tailoring therapeutic strategies. It moves beyond standard diagnostic tools, providing a data-driven approach to precision oncology that directly improves risk management in high-lethality scenarios.

---
*Course Final Exam Project | Author: Dinko Trendafilov | June 2026*