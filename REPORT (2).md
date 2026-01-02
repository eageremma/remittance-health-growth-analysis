# Remittance, Health & Economic Growth --- Executive Report

**Author:** Emmanuel A.\
**Scope:** 1995--2023 country-year panel\
**Repository:**
https://github.com/eagermma/remittance-health-growth-analysis

------------------------------------------------------------------------

## Objective

This project investigates how **personal remittance inflows and health
indicators** influence **economic growth (GDP per capita)** across
countries using econometrics, machine learning, deep learning and NLP.

------------------------------------------------------------------------

## Quick Access to Key Outputs

-   📊 [Model Card](outputs/model_card.md)
-   🧠 [NLP Model Card](outputs/nlp_model_card.md)
-   📈 [Holdout Model Comparison](outputs/holdout_model_comparison.csv)
-   🔁 [Cross Validation Results](outputs/cross_validation_results.csv)
-   🌲 [Random Forest Feature
    Importances](outputs/rf_feature_importances.csv)
-   🧮 [Linear Regression
    Coefficients](outputs/linear_regression_coefficients.csv)
-   🧪 [Causal ATE Estimate](outputs/ate_estimate.csv)
-   📉 [LSTM Metrics](outputs/lstm_metrics.csv)
-   🧬 [PCA Explained Variance](outputs/pca_explained_variance.csv)
-   🖼️ [PCA PC1 vs PC2 Plot](outputs/pca_pc1_pc2_scatter.png)

------------------------------------------------------------------------

## Dataset Summary

Cleaned dataset: [dataset_cleaned.csv](outputs/dataset_cleaned.csv)

------------------------------------------------------------------------

## Key Findings

-   Random Forest significantly outperformed linear regression.
-   Cross-validation confirms strong stability.
-   Causal ATE shows remittance inflows increase GDP per capita.
-   Attention-LSTM provided best time-series forecasting accuracy.
-   NLP topic modeling reveals healthcare and education as dominant
    themes.

------------------------------------------------------------------------

## Conclusion

Remittances are not only correlated with growth --- they **causally
improve economic performance** when combined with strong health and
education systems.
