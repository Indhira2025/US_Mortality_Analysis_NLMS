# Predictive Modeling of Smoking-Related Mortality

## Overview

This project develops and validates machine learning models to predict 5-year mortality risk associated with cigarette smoking using the US-NLMS dataset (n = 493,282; 43 variables). The framework emphasizes risk stratification performance while maintaining statistical interpretability.

------------------------------------------------------------------------
## Background
Cigarette smoking remains a leading preventable cause of death worldwide. Yet, risk varies widely across individuals. Accurately identifying high-risk smokers is critical for targeted public health interventions.


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
-   Top 5%,10%, 20% precision and lift analysis

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

### Summary (Refer the complete summary report - Report.pdf)
  ##### Interesting Key insights:
-   Scalable modeling workflow for large datasets : Apache Arrow/Parquet reduced memory allocation by \~72% and garbage collection events by \~83%, while decreasing runtime from 2.86s to 0.15s.
##### ML Predictive risk model Effective identification of high-risk individuals (codefile: Sourcecode/ML_pred_mortality.Rmd)
-   Machine Learning models have **excellent discrimination** and risk ranking. 
* The AUCs of SmokingStatus model is 0.852 and SmokingStatus + SmokingDuration model is 0.853 are very similar, and the small but statistically significant difference (p ≈ 3.44e-5) indicates SmokingStatus + SmokingDuration model has a slightly higher discriminatory performance.
* Lift analysis demonstrated strong risk stratification performance. The top 10% highest-risk individuals had ~5× higher mortality than average.
##### Logistic Regression Model for Interpretation (codefile: Sourcecode/EDA_regression_source_code.Rmd)
Statistical models provide interpretability, revealing:
 * Everyday smokers have 119% higher mortality (OR=2.19) vs never smokers and Some-day smokers 78% higher mortality (OR=1.78) vs never smokers.
 * Each additional year delay in smoking initiation was associated with a 2.1% reduction in mortality risk.
 * Model fit improved substantially with the inclusion of smoking duration. The Smoking Status + Smoking Duration model demonstrated markedly lower information criteria values (AIC = 49,666.97; BIC = 49,795.82) compared to the Smoking Status only model (AIC = 99,156.09; BIC = 99,297.37).

##### Takeaway: Machine learning delivers predictive power, while statistical modeling provides actionable insight. Together, they enable accurate, interpretable risk assessment.
------------------------------------------------------------------------
