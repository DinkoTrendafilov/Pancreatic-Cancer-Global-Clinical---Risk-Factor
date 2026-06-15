# Multi-Paradigm Survival Analysis and Risk Stratification in Pancreatic Cancer

## 🔬 Project Overview and Clinical Rationale
Pancreatic cancer remains one of the most aggressive and unpredictable malignancies in oncology, characterized by a rapid post-diagnostic hazard progression. Traditional univariate methods fail to capture the concurrent impact of anatomical progression, physiological indicators, and lifestyle confounders. 

This repository hosts an advanced, end-to-end biostatistical data science pipeline designed to forecast survival velocities and evaluate uncertainty across a simulated cohort of **2,000 pancreatic cancer patients**. By leveraging Python's computational ecosystem, this project transitions systematically through non-parametric, semi-parametric, and advanced regularized Bayesian frameworks to isolate the true structural drivers of mortality acceleration.

---

## 🛠️ Multi-Phase Analytical Architecture

### Phase 1: Exploratory Data Analysis & Feature Engineering
* **Log Regularization:** Compressed right-skewed continuous biomarkers (e.g., `CA_19_9_Level`) via logarithmic transformation: $\ln(x + 1)$.
* **Matrix Standardization:** Continuous variables (`Age`, `Tumor_Size_cm`) were mapped onto a uniform scale via Z-score stabilization to prevent magnitude magnitude bias.
* **High-Cardinality Handling:** Categorical elements were factorized, dropping base reference columns to guarantee linear independence and eliminate dummy variable traps.

### Phase 2: Non-Parametric Survival Estimation
* **Kaplan-Meier Estimator:** Formulated longitudinal baseline survival curves across demographic and risk factor groups.
* **Pairwise Log-Rank Testing:** Executed non-parametric screenings to isolate statistically significant differences in survival probability distributions across multi-group lifestyle cohorts (e.g., Joint Smoking/Alcohol metrics).

### Phase 3: Regularized Cox Proportional Hazards Model
* **Semi-Parametric Core:** Implemented a Multivariate Cox Proportional Hazards architecture:
  $$h(t \mid X) = h_0(t) \exp(\beta^T X)$$
* **Ridge ($L_2$) Regularization:** Implemented an $L_2$ mathematical penalty constraint ($\lambda = 0.001$) to handle collinear clinical predictors without losing key metrics.
* **Out-of-Sample Validation:** Executed a Stratified 5-Fold Cross-Validation loop, achieving an outstanding predictive rank-ordering accuracy with a Harrell’s **Concordance Index ($C$-index) of 0.79**.
* **Clinical Stratification:** Calculated continuous Partial Hazard Risk Scores to segment censored (alive) patients into explicit low, intermediate, and high-risk tiers.

### Phase 4: Stochastic Bayesian Simulation Framework
* **Dirichlet Weighting:** Bypassed restrictive, environment-dependent C++ MCMC samplers by engineering a smooth, high-speed **Bayesian Bootstrap Resampling Engine** utilizing continuous weights drawn from a uniform Dirichlet distribution ($\sum w_i = 1$).
* **Posterior Quantification:** Executed 1,000 optimization loops to map full parameters density functions ($P(\beta \mid \text{Data})$).
* **Premium Visualization:** Developed an industrial-grade parallel ridge density configuration (Ridge/Joy Plot) using Gaussian Kernel Density Estimations (KDE) to isolate overlapping risk distributions.

---

## 📊 Paradigm Benchmark Results (Head-to-Head)

The table below compiles the point estimates and 95% uncertainty intervals (Frequentist Confidence Intervals vs. Bayesian Credible Intervals) across advanced cancer stages, setting **Stage I** as the baseline reference strata:

| Clinical Parameter | Bayesian Posterior Mean (Odds Ratio) | Bayesian 95% Credible Interval | Frequentist Coefficient (Hazard Ratio) | Frequentist 95% Confidence Interval | Paradigm Discrepancy (%) |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **Stage II** | 2.71 | [1.79, 3.95] | 2.95 | [1.92, 4.54] | + 8.9% |
| **Stage III** | 7.37 | [4.93, 10.73] | 8.42 | [5.23, 13.56] | + 14.2% |
| **Stage IV** | 24.13 | [15.49, 36.19] | 28.67 | [17.34, 47.42] | + 18.8% |

### 🔍 Epistemological Insight on Model Deviations
A systematic divergence is observed where the continuous Cox Hazard Ratios are higher than the terminal Bayesian Odds Ratios. This is mathematically expected: 
* The **Bayesian Odds Ratio (OR)** evaluates binary, cumulative survival probability at a static terminal threshold.
* The **Cox Hazard Ratio (HR)** tracks the instantaneous velocity of failure risk at any time $t$, conditioning the calculation exclusively on the changing risk-set. Due to the high mortality speed of pancreatic malignancies, the longitudinal model captures compounding time-dependent risk, resulting in higher multipliers.

---

## 📈 Key Clinical Findings
1. **Exponential Staging Risk:** Anatomical cell proliferation completely dictates survival velocity. Progression to Stage IV causes a critical **~24x to ~29x risk explosion** compared to early-stage baselines.
2. **Biomarker Dominance:** Intrinsic tumor scale, continuous staging metrics, and continuous metabolic biomarkers completely drown out baseline demographic attributes and historical lifestyle traits once the disease is diagnosed.
3. **Interval Interpretation:** The 95% Bayesian Credible Intervals establish a direct probability statement ("There is a 95% actual probability that the true risk falls here"), proving optimal utility for bedside clinical risk communication compared to frequentist confidence abstractions.

---

## 📂 Project Structure
* `cox_proportional_pancreatic_cancer.ipynb` -> Multivariate regularized Cox PH model, cross-validation, and clinical stage forecasting curves.
* `bayesian_survival_analysis.ipynb` -> Stochastic Bayesian Bootstrap framework and parameter uncertainty sampling.
* `final_comparison_and_conclusion.ipynb` -> Head-to-head multi-paradigm benchmark, mathematical divergence matrix, and visual charts.
* `pancreatic_cancer_dataset_scaled_processed.csv` -> Globally standardized clinical data matrix optimized for future pipeline deployments.

---

## 🚀 How to Run the Environment
Clone the repository and install the standard numerical computing requirements:
```bash
git clone [https://github.com/YOUR_USERNAME/PancreaticCancer.git](https://github.com/YOUR_USERNAME/PancreaticCancer.git)
cd PancreaticCancer
pip install numpy pandas matplotlib scipy scikit-learn statsmodels lifelines
