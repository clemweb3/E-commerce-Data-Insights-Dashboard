# 📊 E-Commerce Sales and Returns Analytics Dashboard
End-to-end analysis of e-commerce sales transactions with data cleaning, KPI generation, and an interactive Tableau dashboard.

### Project Overview
This project builds an end-to-end analytics pipeline for e-commerce data:

- Starting from raw transactional records  
- Performing data quality checks and feature engineering  
- Training a predictive model using CatBoost to estimate product return risk  
- Exporting a unified dataset for Tableau dashboards  

### The goal is to answer key business questions:
1. Which products and categories are most prone to returns?  
2. How do delivery speed, discounts, and customer demographics affect return behavior?  
3. Can we predict return risk at the order level to guide business decisions?  

### Pipeline Steps
1. **Data Ingestion and Validation**: Load raw CSV files, check for missing values, duplicates, and outliers.  
2. **Feature Engineering**: Create customer histories, product return rates, recency features, discount buckets, and delivery speed segments.  
3. **Predictive Modeling**: Train a CatBoost classifier with both numeric and categorical features.  
4. **Threshold Tuning**: Optimize the classification threshold for better recall of return cases.  
5. **Feature Importance**: Identify top drivers of returns including price per unit, total cost ratio, and customer demographics.  
6. **Unified Export**: Save the enriched dataset with predictions and metadata for Tableau integration.  

### Key Insights
Top drivers of returns:

1. price_per_unit  
2. total_cost_ratio  
3. customer_age  
4. days_since_last_order  
5. customer_tenure_days  

### Business Takeaway
- High unit prices and costly shipping ratios strongly influence return likelihood.  
- Customer demographics and purchase recency contribute to prediction strength.  
- These insights help guide product strategy, logistics decisions, and customer engagement.  

### 🤖 Why CatBoost?
CatBoost was chosen because:

1. It handles categorical features natively, reducing preprocessing work.  
2. It performs well with imbalanced datasets, which is common in return prediction.  
3. It provides interpretable feature importance that integrates cleanly into dashboards.  

### What I Learned
- Predicting rare events like returns is challenging because accuracy can mask poor minority-class performance. Metrics such as ROC-AUC offer better clarity.  
- Feature engineering has a major impact on improving recall for rare outcomes.  
- CatBoost keeps the modeling pipeline straightforward while producing interpretable results.  
- Even if model performance is modest, feature importance remains valuable for business storytelling.  

### References
1. Sayyad, J. K., Attarde, K., and Saadouli, N. (2024). Optimizing e-commerce supply chains with categorical boosting: A predictive modeling framework. *IEEE Access, 12*, 134549–134567. https://doi.org/10.1109/access.2024.3447756  
2. https://www.geeksforgeeks.org/machine-learning/e-commerce-product-recommendations-using-catboost/
