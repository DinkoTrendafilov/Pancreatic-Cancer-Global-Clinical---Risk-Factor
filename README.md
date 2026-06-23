# 🏥 Pancreatic Cancer Risk Prediction

**An End-to-End Machine Learning Pipeline for Early Risk Assessment**

---

## 📌 Project Overview

Pancreatic cancer has a 5-year survival rate of ~10%. This project builds a **cost-sensitive ML pipeline** to predict pancreatic cancer risk using clinical data. The model prioritizes **patient safety** by minimizing False Negatives (FN = 0).

**Objective:** Detect high-risk patients early | **Goal:** FN = 0, FP < 40

---

## 🏆 Final Model Performance

| Metric | Value | Status |
|--------|-------|--------|
| **Model** | Random Forest (45 features) | 🏆 Champion |
| **False Negatives (FN)** | 0 | ✅ PERFECT |
| **False Positives (FP)** | 39 | ✅ GOOD |
| **Recall (Sensitivity)** | 1.000 | ✅ PERFECT |
| **AUC Score** | 0.8661 | ✅ GOOD |
| **Optimal Threshold** | 0.294 | ✅ |
| **Total Cost** | 390,000 | ✅ OPTIMAL |

---

## 📊 Key Experiments & Results

| Experiment | FN | FP | Cost | Winner |
|------------|----|----|------|--------|
| BASE (45 features) | 0 | 39 | 390,000 | 🏆 |
| XGBoost | 0 | 46 | 460,000 | ❌ |
| Top 5 Features | 0 | 47 | 470,000 | ❌ |
| Feature Engineering (59 features) | 0 | 41 | 410,000 | ❌ |

**Conclusion:** The original 45-feature Random Forest model is the clear winner. **"Keep it simple!"** 🔥

---

## 💰 Cost-Sensitive Optimization

| Error Type | Cost | Clinical Impact |
|------------|------|-----------------|
| **False Negative (FN)** | 100,000,000 | Missed high-risk patient - UNACCEPTABLE |
| **False Positive (FP)** | 10,000 | Unnecessary tests - MANAGEABLE |

> **"Missing a high-risk patient is catastrophic; a false alarm is inconvenient."**

---

## 🩺 Clinical Risk Stratification

| Risk Level | Probability | Action |
|------------|-------------|--------|
| LOW | < 40% | Regular Monitoring |
| MEDIUM | 40-60% | Additional Tests |
| HIGH | 60-80% | Specialist Referral |
| CRITICAL | > 80% | Immediate Intervention |

---

## How to Use

```python
import joblib
import pandas as pd

# Load model and threshold
model = joblib.load('pancreatic_cancer_best_model.pkl')

# Load threshold
with open('optimal_threshold.txt', 'r') as f:
    threshold = float(f.readline().split(':')[1].strip())

# Predict
new_patient = pd.DataFrame({...})  # Your 45 features
probability = model.predict_proba(new_patient)[:, 1][0]
risk = "HIGH RISK" if probability >= threshold else "LOW RISK"


## 📊 Visualizations

- **Confusion Matrix:** FP=39, FN=0 (Zero missed high-risk patients)
- **ROC Curve:** AUC = 0.8661 (Excellent discriminatory power)
- **Feature Importance:** Top predictors - Tumor Size, CA 19-9, Cancer Stage, BMI

---

## 🔮 Future Work

- **Deploy as API** (FastAPI) for real-time clinical predictions
- **SHAP interpretability** for patient-specific explanations
- **External validation** on other clinical datasets
- **DeepSurv** for dynamic survival curve predictions

---

## 👨‍⚕️ Author

**Dinko Trendafilov** | [GitHub](https://github.com/dinko-trendafilov)

---

**Made with ❤️ for better patient outcomes**

*Last Updated: June 2026*