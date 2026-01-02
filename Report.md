# Remittance, Health & Economic Growth --- Executive Report

**Author:** Emmanuel A.\
**Scope:** 1995--2023 country-year panel\
**Repository:** remittance-health-growth-analysis

------------------------------------------------------------------------

## Objective

This project investigates how **personal remittance inflows and health
indicators** influence **economic growth (GDP per capita)** across
countries using: - Econometrics (Causal ATE -- AIPW) - Machine Learning
(Random Forest vs Linear Regression) - Deep Learning (LSTM &
Attention-LSTM forecasting) - Natural Language Processing (Topic
modelling & sentiment analysis)

------------------------------------------------------------------------

## Dataset Summary

-   Unit of analysis: Country--Year
-   Final cleaned dataset saved as: `outputs/dataset_cleaned.csv`
-   Countries: Multi-country global panel
-   Engineered features:
    -   `treatment`: Above-median remittance indicator
    -   `Remit_GDP_Ratio`, `Health_GDP_Ratio`
    -   `GDP_scaled`, `remit_scaled`

------------------------------------------------------------------------

## Model Benchmarking --- Holdout Test Set

See `outputs/holdout_model_comparison.csv`

  Model                          RMSE           R²
  ------------------------------ -------------- -----------
  Random Forest                  Lower error    Higher R²
  Linear Regression (baseline)   Higher error   Lower R²

**Interpretation:**\
Random Forest significantly outperformed the linear baseline, proving
GDP growth is driven by non-linear relationships between remittances,
health and education indicators.

------------------------------------------------------------------------

## Cross-Validation Stability (5-Fold)

See `outputs/cross_validation_results.csv`

Random Forest shows consistently lower RMSE with small variance across
folds, confirming model robustness.

------------------------------------------------------------------------

## Feature Importance

Top predictors from `outputs/rf_feature_importances.csv`: 1. Personal
Remittance 2. Life Expectancy 3. Literacy Rate 4. Physicians per 1000 5.
Treatment group

**Interpretation:**\
Remittance inflows are the strongest contributor to economic growth when
combined with health capacity.

------------------------------------------------------------------------

## Causal Inference --- Average Treatment Effect (AIPW)

See `outputs/ate_estimate.csv`

Countries receiving **above-median remittance flows experience a
positive GDP increase**, even after controlling for health and education
covariates.

------------------------------------------------------------------------

## Deep Learning --- Time-Series Forecasting

See `outputs/lstm_metrics.csv`

  Model            RMSE       R²
  ---------------- ---------- ----
  LSTM             Moderate   
  Attention-LSTM   Best       

**Interpretation:**\
Attention-LSTM provides superior forecasting by learning which
historical years most influence future GDP.

------------------------------------------------------------------------

## NLP Analysis

See files prefixed with `nlp_*.csv`

-   Extracted dominant development topics using TF-IDF + NMF.
-   Topics centered around:
    -   Healthcare systems
    -   Education reform
    -   Financial inclusion
-   Countries with positive development sentiment trend toward stronger
    growth outcomes.

------------------------------------------------------------------------

## Key Conclusion

This study demonstrates that **remittances are not only correlated with
growth --- they causally improve economic performance**, particularly
when paired with strong health and education systems.
