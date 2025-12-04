# 📊 E‑Commerce Sales & Returns Analytics Dashboard
End-to-end analysis of e-commerce sales transactions with data cleaning, KPI generation, and interactive Tableau dashboard.

### Project Overview

This project builds an end‑to‑end analytics pipeline for e‑commerce data:

    - Starting from raw transactional records
    - Performing data quality checks and feature engineering
    - Training a predictive model (CatBoost) to estimate product return risk
    - Exporting a unified dataset for Tableau dashboards

### The goal is to answer key business questions:

    1. Which products and categories are most prone to returns?
    2. How do delivery speed, discounts, and customer demographics affect return behavior?
    3. Can we predict return risk at the order level to guide business decisions?

### Pipeline Steps

    1. Data Ingestion & Validation: Load raw CSV files, check for missing values, duplicates, and outliers.
    2. Feature Engineering: Create customer histories, product return rates, recency features, discount buckets, and delivery speed segments.
    3. Predictive Modeling: Train a CatBoost classifier with both numeric and categorical features.
    4. Threshold Tuning: Optimize the classification threshold for better recall of return cases.
    5. Feature Importance: Identify top drivers of returns (e.g., price per unit, total cost ratio, customer age).
    6. Unified Export: Save enriched dataset with predictions, feature importance scores, and metadata for Tableau integration.

### Key Insights

    Top Drivers of Returns:

        1. price_per_unit
        2. total_cost_ratio
        3. customer_age
        4. days_since_last_order
        5. customer_tenure_days

 ### Business Takeaway:

        - High unit prices and costly shipping ratios strongly influence return likelihood.
        - Customer demographics and purchase recency also play a role.
        - These insights can guide product strategy, logistics, and customer engagement.

### 🤖 Why CatBoost?

CatBoost was chosen because:

    1. It handles categorical features natively (no heavy preprocessing needed).
    2. It is robust to imbalanced datasets (returns are rare events).
    3. It provides interpretable feature importance, which feeds directly into dashboards.

### What I learned
  - Predicting rare events like returns is inherently difficult — accuracy can look fine, but ROC‑AUC reveals the true discriminative power.
  - Feature engineering (recency, streaks, product history) is critical for improving recall of minority classes.
  - CatBoost’s ability to handle categorical features natively simplified the pipeline and still produced interpretable feature importance.
  - Even when predictive power is modest, feature importance rankings are valuable for business storytelling and dashboard integration.
  - 
##### References: 

[1.] Sayyad, J. K., Attarde, K., & Saadouli, N. (2024). Optimizing e-commerce supply chains with categorical boosting: A predictive modeling framework. IEEE Access, 12, 134549–134567. https://doi.org/10.1109/access.2024.3447756 
[2.] https://www.geeksforgeeks.org/machine-learning/e-commerce-product-recommendations-using-catboost/


