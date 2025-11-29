# Telco-Customer-Churn-XGBoost

This project is an end-to-end Machine Learning solution focused on **predicting customer churn** within the telecom sector and developing actionable retention strategies. We used the Telco Customer Churn dataset.

##  Project Goal

The primary goal was to build a highly **sensitive classification model** (maximizing Recall) to accurately flag 'at-risk' customers so that timely retention efforts can be deployed.

---

##  Methodology & Model Performance

### 1. Data Processing and Baseline
* **Imbalance Handling:** The target variable (Churn $\approx 26.54\%$) was imbalanced. This was addressed using the `scale_pos_weight` parameter in XGBoost.
* **Initial Model:** The untuned XGBoost model achieved a Churn Recall of **$0.67$**.

### 2. Hyperparameter Tuning (Optimization)
* **Technique:** **Grid Search** was performed to optimize hyperparameters.
* **Best Parameters:** `{'gamma': 0, 'learning_rate': 0.05, 'max_depth': 3, 'n_estimators': 200}`.

### 3. Final Tuned Model Evaluation

| Metric | Previous Model (Untuned) | **Tuned Final Model** |
| :--- | :--- | :--- |
| **Accuracy** | $0.76$ | **$0.75$** |
| **Recall (Churn - Class 1)** | $0.67$ | **$0.81$** |
| **Precision (Churn - Class 1)** | $0.54$ | **$0.51$** |

* **Result:** Tuning successfully increased **Recall by 14% points** (from 0.67 to 0.81). This improvement significantly reduced **False Negatives** (missed churn cases) from 187 to 106, making the model highly valuable for business use.

---

##  Key Churn Drivers & Business Recommendation

Feature Importance analysis identified the factors most strongly correlated with customer departure: 

1.  **Financial Factors:** **`MonthlyCharges`** is the single strongest driver, followed by low **`tenure`** and high **`TotalCharges`**.
2.  **Payment Risk:** The payment method **`Electronic check`** is significantly associated with higher churn risk.

###  Retention Strategy

Leveraging the model's high Recall ($0.81$), the company should implement a **Targeted Retention Program**:

* **Offer Incentives:** Target customers with high `MonthlyCharges` and those using `Electronic check` with **long-term contract discounts** or **loyalty upgrades**.
* **Strategy Validation:** Implement **A/B Testing** to measure the financial impact and effectiveness of these targeted campaigns before full deployment.
