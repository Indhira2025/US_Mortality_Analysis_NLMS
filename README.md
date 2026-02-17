

# Predictive Modeling of Smoking-Related Mortality

## Overview
This project develops and validates machine learning models to predict 5-year mortality risk associated with cigarette smoking using the US-NLMS dataset (n = 493,282; 43 variables). The framework emphasizes risk stratification performance while maintaining statistical interpretability.

---

## Objectives
- Build predictive models to estimate mortality risk.
- Evaluate discrimination performance using cross-validation and ROC/AUC.
- Identify high-risk individuals through percentile-based risk ranking.
- Quantify smoking-related mortality effects using interpretable statistical models.
- Optimize large-scale data processing efficiency.

---

## Dataset
- Source: US-NLMS
- Observations: 493,282
- Variables: 43 demographic and behavioral features
- Outcome: 5-year all-cause mortality (binary)

---

## Methods

### 1. Data Processing
- Large-scale data handled using Apache Arrow/Parquet.
- Achieved ~65% reduction in I/O time.
- Categorical encoding and missing value handling performed in R.

### 2. Predictive Modeling
- Logistic regression (classification framework)
- 5-fold cross-validation
- Performance metric: ROC/AUC (AUC ≈ 0.85)

### 3. Risk Stratification
- Probability-based ranking
- Top 5%, 10%, 20% precision and lift analysis

### 4. Model Interpretation
- Adjusted odds ratios from logistic regression
- AIC/BIC for model comparison
- Smoking status and duration effect quantification

---

## Tech Stack
- R
- caret
- pROC
- Apache Arrow / Parquet

---

## Results
- Strong discrimination performance (AUC ≈ 0.85)
- Effective identification of high-risk individuals
- Scalable modeling workflow for large datasets

---

