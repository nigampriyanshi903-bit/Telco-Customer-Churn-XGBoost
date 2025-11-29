# Telco-Customer-Churn-XGBoost

## Project Overview

This is an end-to-end Machine Learning project focused on **Customer Churn Prediction** using the IBM Telco Customer Churn dataset. The goal is to build a high-performance classification model to identify 'at-risk' customers and derive actionable business strategies for retention.

## Key Techniques Used

* **Model:** Gradient Boosting Machine (**XGBoost**)
* **Problem:** Binary Classification (Imbalanced data, Churn Rate $\approx 26.54\%$)
* **Preprocessing:** One-Hot Encoding, Handling missing values (e.g., in `TotalCharges`), and scaling.
* **Imbalance Handling:** Used `scale_pos_weight` in XGBoost for better recall.
* **Output:** Model evaluation, Feature Importance analysis, and A/B Testing strategy.

##  Model Performance Highlights

The XGBoost model was trained and evaluated on a test set of 2113 samples, prioritizing the identification of churning customers (Class 1).

| Metric | Churn (Class 1) |
| :--- | :--- |
| **Recall** | **$0.67$** |
| **Precision** | **$0.54$** |
| **Accuracy** | $0.76$ |

##  Key Findings & Business Insights

Feature Importance analysis (F-Score) clearly identified the primary drivers of customer churn:

1.  **MonthlyCharges:** The single strongest predictor of churn.
2.  **TotalCharges** / **tenure:** Low tenure (new customers) and overall high spending indicate high risk.
3.  **PaymentMethod_Electronic check:** This payment method is associated with higher churn risk.

###  Business Recommendation

A strategy focused on reducing **Monthly Charges** for high-risk customers (e.g., targeted discounts) and incentivizing a shift away from Electronic Check payments is recommended.
