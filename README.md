# 🏥 Pancreatic Cancer Risk Prediction

## An End-to-End Machine Learning Pipeline for Early Risk Assessment

[![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)](https://www.python.org/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-1.3.0-orange.svg)](https://scikit-learn.org/)
[![XGBoost](https://img.shields.io/badge/XGBoost-1.7.0-red.svg)](https://xgboost.readthedocs.io/)
[![MLflow](https://img.shields.io/badge/MLflow-2.3.0-green.svg)](https://mlflow.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

---

## 📋 Table of Contents
- [Project Overview](#-project-overview)
- [Key Findings](#-key-findings)
- [Repository Structure](#-repository-structure)
- [Installation & Setup](#-installation--setup)
- [Dataset](#-dataset)
- [Notebooks Overview](#-notebooks-overview)
- [Models Evaluated](#-models-evaluated)
- [Performance Metrics](#-performance-metrics)
- [Cost-Sensitive Optimization](#-cost-sensitive-optimization)
- [Feature Engineering Experiments](#-feature-engineering-experiments)
- [Clinical Decision Support](#-clinical-decision-support)
- [Visualizations](#-visualizations)
- [How to Use the Model](#-how-to-use-the-model)
- [Future Work](#-future-work)
- [License](#-license)
- [Author](#-author)

---

## 📌 Project Overview

Pancreatic cancer remains one of the most lethal malignancies globally, with a 5-year survival rate of approximately 10%. Early detection and accurate risk stratification are critical for improving patient outcomes. This project develops a **cost-sensitive machine learning pipeline** to predict pancreatic cancer risk using clinical and demographic data.

### 🎯 Primary Objectives

1. **Minimize False Negatives (FN)** - Ensure no high-risk patient is missed (FN = 0)
2. **Maintain High Precision** - Balance sensitivity with specificity (FP < 40)
3. **Optimize Clinical Utility** - Align model predictions with real-world medical workflows
4. **Ensure Reproducibility** - Use MLflow for experiment tracking and model registry

### 🚀 Key Features

- ✅ **Cost-Sensitive Learning** - Optimized for clinical decision-making
- ✅ **MLflow Integration** - Full experiment tracking and model registry
- ✅ **Automated Preprocessing** - Handles numeric, categorical, and ordinal features
- ✅ **Comprehensive Model Comparison** - Random Forest, XGBoost, Decision Tree
- ✅ **Feature Importance Analysis** - Identifies key clinical predictors
- ✅ **Risk Stratification** - 4-tier risk classification system
- ✅ **Production-Ready** - Serialized pipeline with joblib

---

## 🏆 Key Findings

| Metric | Best Model | Value |
|--------|------------|-------|
| **Model** | Random Forest | - |
| **False Negatives (FN)** | ✅ **0** | 0.00% |
| **False Positives (FP)** | ✅ **39** | 9.75% |
| **Recall (Sensitivity)** | ✅ **1.000** | 100% |
| **AUC Score** | ✅ **0.8661** | - |
| **Optimal Threshold** | ✅ **0.294** | - |
| **Total Cost** | ✅ **390,000** | - |

### 🎯 Why This Matters

> **"Zero false negatives means no high-risk patient is missed."**

This model achieves the critical clinical goal of **identifying every patient at risk**, while maintaining a manageable false positive rate of just 9.75%.

---

---

## 💻 Installation & Setup

### Prerequisites
- Python 3.10+
- pip (package manager)

### Clone the Repository
```bash
git clone https://github.com/DinkoTrendafilov/pancreatic-cancer-prediction.git
cd pancreatic-cancer-prediction

# On macOS/Linux
python3 -m venv venv
source venv/bin/activate

# On Windows
python -m venv venv
venv\Scripts\activate


