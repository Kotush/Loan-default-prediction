# Loan-default-prediction

This project aims to predict the likelihood of a loan default using various machine learning models, focusing on improving predictive performance through feature engineering and model evaluation. Two main models were developed and compared: a **Baseline model** and a more advanced **Challenger model**.

---

## Problem Statement

The goal is to accurately classify whether a borrower will default on their loan, using features like FICO score, loan amount, credit history, and more. The ability to detect defaults early can significantly reduce financial risk for lenders.

---

## Models Overview

### 1. Baseline Model
- **Algorithm**: Logistic Regression
- **Evaluation Metrics**:
  - Accuracy: Moderate
  - ROC AUC: Lower than the challenger
  - Precision-Recall AUC: Significantly lower
- **Insights**:
  - Served as a reference point.
  - Performed reasonably well but showed limitations, especially in capturing complex relationships between features.
  - Struggled to balance false positives and false negatives.

### 2. Challenger Model
- **Algorithm**: Random Forest
- **Evaluation Metrics**:
  - **Accuracy**: 95%
  - **Precision (class 1)**: 0.81
  - **Recall (class 1)**: 0.74
  - **F1 Score (class 1)**: 0.77
  - **ROC AUC**: Excellent (visibly close to 1.0)
  - **Average Precision (PR AUC)**: 0.82
- **Feature Importance**:
  - The most critical features included `last_fico_range_low`, `last_credit_pull_d_days`, and `out_prncp_inv`.

---

##  Comparison

| Metric                  | Baseline (LogReg) | Challenger (RF) |
|------------------------|-------------------|------------------|
| Accuracy               | Moderate          | **0.95**         |
| Precision (class 1)    | Lower             | **0.81**         |
| Recall (class 1)       | Lower             | **0.74**         |
| F1 Score (class 1)     | Lower             | **0.77**         |
| ROC AUC                | Lower             | **High (~1.0)**  |
| PR AUC                 | Lower             | **0.82**         |

**Challenger model clearly outperformed the baseline**, particularly in precision-recall balance, indicating strong capability in identifying true defaults.

---

##  How to Use

1. Clone the repository
2. Install required libraries
3. Open and run the notebooks in order: 
   Data Prep - EDA →  → Baseline → Challenger
4. Evaluate model outputs and visualizations

---

##  Next Steps

- Implement XGBoost or LightGBM as a third comparison
- Hyperparameter tuning
- Consider feature selection to reduce noise
- Explore SHAP values for explainability


##  Key Takeaway

The Random Forest challenger model demonstrates high predictive power, especially for unbalanced datasets like loan defaults. Its use of ensemble learning helps capture complex patterns that logistic regression may miss.



