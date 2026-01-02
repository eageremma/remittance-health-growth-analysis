
# Model Card — Remittance, Health & Growth Thesis Pipeline

**Generated:** 2026-01-02 20:23:41  
**Dataset path:** `C:/Users/User/Downloads/Thesis Main Data.xlsx`  
**Year filter:** 1995–2023  
**Unit of analysis:** Country-year panel  
**Outcome:** `GDP_scaled` (z-score of GDP per capita)  
**Treatment:** `treatment = 1` if Remittance > median (136,212,684.1781), else 0

---

## Objective
Predict and analyze GDP per capita (scaled) using remittances and key development indicators, compare against a transparent baseline, evaluate stability with cross-validation, and include causal ATE estimation.

---

## Data Processing
- Dropped rows missing: Year, Country, Remittance, GDP  
- Engineered ratios: `Remit_GDP_Ratio`, `Health_GDP_Ratio` (safe division; inf→NaN)  
- Global z-score scaling: `GDP_scaled`, `remit_scaled`

**Clean dataset shape:** (1692, 16)  
**Modeling dataset rows:** 175

---

## Model Comparison (Holdout Test Set)
| Model | RMSE | MSE | R² |
|---|---:|---:|---:|
| Random Forest | 0.7309 | 0.5342 | 0.7355 |
| Linear Regression (baseline) | 0.8912 | 0.7942 | 0.6068 |

---

## Cross-Validation Stability (5-fold)
**Random Forest:** RMSE 0.7713 ± 0.2983, R² 0.5380 ± 0.3717  
**Linear Regression:** RMSE 0.9714 ± 0.3206, R² 0.4200 ± 0.1441  

---

## Causal Estimate (AIPW)
**ATE on GDP_scaled:** 6.5451  
Meaning: average expected change in GDP_scaled when moving from low to high remittance group (median split), controlling for covariates.

---

## Feature Influence
**Top Random Forest importances**
Life_Expectancy       0.6742
Personal Remittance   0.1167
Physicians_per_1000   0.1081
Literacy_Rate         0.0995
treatment             0.0015

**Top Linear Regression coefficients (abs-ranked)**
Physicians_per_1000    0.8228
treatment             -0.2264
Life_Expectancy        0.1161
Personal Remittance   -0.0318
Literacy_Rate         -0.0074

---

## Artifacts Saved (audit-ready)
- `dataset_cleaned.csv`
- `summary_overall.csv`, `summary_by_country.csv`
- `cross_validation_results.csv`, `holdout_model_comparison.csv`
- `rf_feature_importances.csv`, `linear_regression_coefficients.csv`
- `ate_estimate.csv`
- `pca_explained_variance.csv`, `pca_loadings.csv`
- `test_predictions_rf_vs_linear.csv`
- `lstm_test_predictions.csv`, `attention_lstm_test_predictions.csv`, `lstm_metrics.csv` (if TF available)

**Outputs folder:** `C:\Users\User\thesis_outputs_py`
