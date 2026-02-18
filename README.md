# Predictive Modeling of Smoking-Related Mortality

## Overview

This project develops and validates machine learning models to predict 5-year mortality risk associated with cigarette smoking using the US-NLMS dataset (n = 493,282; 43 variables). The framework emphasizes risk stratification performance while maintaining statistical interpretability.

------------------------------------------------------------------------

## Objectives

-   Build predictive models to estimate mortality risk.
-   Evaluate discrimination performance using cross-validation and ROC/AUC.
-   Identify high-risk individuals through percentile-based risk ranking.
-   Quantify smoking-related mortality effects using interpretable statistical models.
-   Optimize large-scale data processing efficiency.

------------------------------------------------------------------------

## Dataset

-   Source: US-NLMS
-   Observations: 493,282
-   Variables: 43 demographic and behavioral features
-   Outcome: 5-year all-cause mortality (binary)

------------------------------------------------------------------------

## Methods

### 1. Data Processing

-   Large-scale data handled using Apache Arrow/Parquet.
-   Categorical encoding and missing value handling performed in R.

### 2. Predictive Modeling

-   Logistic regression (classification framework)
-   5-fold cross-validation
-   Performance metric: ROC/AUC

### 3. Risk Stratification

-   Probability-based ranking
-   Top 10% precision and lift analysis

### 4. Model Interpretation

-   Adjusted odds ratios from logistic regression
-   AIC/BIC for model comparison
-   Smoking status and duration effect quantification

------------------------------------------------------------------------

## Tech Stack

-   R
-   pROC
-   Apache Arrow / Parquet

------------------------------------------------------------------------

## Results 

#### (Please refer Report.pdf)

Summary (Refer the complete summary report - Report.pdf)

-   Scalable modeling workflow for large datasets : Apache Arrow/Parquet reduced memory allocation by \~72% and garbage collection events by \~83%, while decreasing runtime from 2.86s to 0.15s.

-   ML Predictive risk model Effective identification of high-risk individuals (codefile: Sourcecode/ML_pred_mortality.Rmd)

    The AUCs of SmokingStatus model`rocCV1` (0.852) and SmokingStatus + SmokingDuration model `rocCV2` (0.853) are very similar, and the small but statistically significant difference (p ≈ 3.44e-5) indicates `rocCV2` has a slightly higher discriminatory performance.

-   Logistic Regression Model for Interpretation (codefile: Sourcecode/EDA_regression_source_code.Rmd)

------------------------------------------------------------------------
