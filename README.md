# 📊 🚨  Financial Fraud Detection & Risk Analytics System using Machine Learning

## 🚀 Overview

This project focuses on detecting fraudulent financial transactions using **data analysis, feature engineering, and machine learning techniques**. The objective is to identify suspicious transaction patterns and build a predictive system that classifies transactions as **fraudulent or legitimate**.

The project combines **Exploratory Data Analysis (EDA)**, **feature engineering**, and **machine learning models**, along with an upcoming **Power BI dashboard** for interactive insights.

---

## 🎯 Objectives

* Analyze transaction data to identify fraud patterns
* Perform data cleaning and preprocessing
* Engineer meaningful features to capture abnormal behavior
* Build and evaluate machine learning models for fraud detection
* Handle class imbalance using resampling techniques
* Deliver actionable insights and recommendations

---

## 📂 Dataset Description

The dataset contains financial transaction records with the following key features:

* `step` → Time step of transaction
* `type` → Transaction type (PAYMENT, TRANSFER, CASH_OUT, etc.)
* `amount` → Transaction amount
* `nameOrig` → Sender ID
* `oldbalanceOrg`, `newbalanceOrig` → Sender balances
* `nameDest` → Receiver ID
* `oldbalanceDest`, `newbalanceDest` → Receiver balances
* `isFraud` → Target variable (1 = Fraud, 0 = Not Fraud)
* `isFlaggedFraud` → System-flagged fraud

---

## 🧠 Problem Statement

Fraudulent transactions are rare but highly impactful. Traditional rule-based systems struggle to detect complex and evolving fraud patterns.

This project aims to develop a **data-driven fraud detection system** using machine learning to automatically identify suspicious transactions.

---

## 🧹 Data Cleaning & Preparation

* Removed duplicate records
* Converted categorical variables into numerical format
* Prepared dataset for machine learning models
* Handled inconsistencies in transaction data

---

## ⚙️ Feature Engineering

To improve model performance, several new features were created:

* `errorOrig` → Difference between expected and actual sender balance
* `errorDest` → Difference in receiver balance
* `balance_change_orig` → Sender balance change
* `balance_change_dest` → Receiver balance change
* `amount_to_balance` → Transaction-to-balance ratio
* `is_large_txn` → Flag for high-value transactions

These engineered features help capture hidden fraud patterns.

---

## 📊 Exploratory Data Analysis (EDA)

### Fraud vs Non-Fraud (Distribution)

**Insight:** Fraud cases are negligible compared to non-fraud, indicating severe class imbalance.
**Strategy:** Apply resampling techniques (e.g., SMOTE) or use recall-focused evaluation metrics.

---

### Transaction Type vs Fraud (Segmentation)

**Insight:** Fraud occurs mainly in CASH_OUT and TRANSFER transactions, with negligible cases in others.
**Strategy:** Focus fraud detection and monitoring on these high-risk transaction types.

---

### Transaction Amount Distribution (Distribution)

**Insight:** Most transactions are small, with a long tail of high-value transactions.
**Strategy:** Apply log transformation or scaling to reduce skewness and improve model performance.

---

### Fraud vs Amount (Relationship)

**Insight:** Fraud cases are more frequent in lower transaction amounts compared to high-value transactions.
**Strategy:** Include transaction amount thresholds and derived features in fraud detection models.

---

### Old Balance vs Fraud (Relationship)

**Insight:** Fraud cases exhibit wider variation and extreme outliers in account balances.
**Strategy:** Use balance-based anomaly detection as a key fraud indicator.

---

### Error in Origin Balance (Distribution)

**Insight:** Most origin balance errors are near zero, with a few extreme deviations.
**Strategy:** Flag large deviations as potential fraud signals.

---

### Error in Destination Balance (Distribution)

**Insight:** Destination balance errors are mostly minimal, concentrated near zero.
**Strategy:** Monitor rare large deviations as anomaly indicators.

---

### Correlation Heatmap (Relationships)

**Insight:** Strong correlations exist between balances and transaction amounts, but weak correlation with fraud labels.
**Strategy:** Engineer derived features (e.g., balance differences) to improve model detection capability.

---

### Large Transactions vs Fraud (Segmentation)

**Insight:** Most fraud occurs in smaller transactions, while large transactions are fewer and generally safer.
**Strategy:** Prioritize monitoring of smaller transactions while tracking anomalies in large ones.

---
## 📊 Exploratory Data Analysis (EDA)

Fraud vs Non-Fraud (Distribution)  
**Insight:** Fraud cases are negligible compared to non-fraud.  
**Strategy:** Apply resampling techniques (e.g., SMOTE) or use recall-focused metrics.  

...

## 📊 Chart Visualizations

![Fraud Distribution](images/fraud_distribution.png)
![Transaction Type vs Fraud](images/type_vs_fraud.png)
![Amount vs Fraud](https://github.com/azmattanveer409/Financial-Fraud-Detection-Risk-Analytics-System-using-Machine-Learning/blob/3600729c673cbb4f0b470a833e8b37efdb4c7cea/Amount%20vs%20Fraud.png)
![Correlation Heatmap](https://github.com/azmattanveer409/Financial-Fraud-Detection-Risk-Analytics-System-using-Machine-Learning/blob/151b87d8f6b92ff169898c39567840fe8a0d4d1d/Correlation%20Heatmap.png)

---

## 🤖 Machine Learning Approach

### 🔹 Problem Type

**Supervised Learning → Classification**

### 🔹 Models Used

* Logistic Regression (baseline model)
* Random Forest (advanced model)

### 🔹 Data Handling

* Train-test split (80% training, 20% testing)
* SMOTE applied to address class imbalance

---

## 📈 Model Evaluation

The models were evaluated using:

* **Confusion Matrix** → Measures correct and incorrect predictions
* **Precision** → Accuracy of fraud predictions
* **Recall (Critical)** → Ability to detect actual fraud cases
* **F1-Score** → Balance between precision and recall
* **ROC-AUC Score** → Overall model performance

👉 The Random Forest model demonstrated strong performance in identifying fraud patterns.

---

## 🔍 Key Insights

1. Fraud cases are extremely rare, indicating severe class imbalance.
2. Fraud is concentrated in CASH_OUT and TRANSFER transaction types.
3. Most transactions are small; fraud is more common in lower-value transactions.
4. Fraudulent behavior is associated with abnormal balance variations.
5. Large deviations in balance errors indicate potential anomalies.
6. Strong relationships exist between balances and transaction amounts.
7. Smaller transactions require more focused fraud monitoring.

---

## 🚀 Strategic Recommendations

1. Apply resampling techniques or class-weighted metrics to effectively handle class imbalance.
2. Prioritize fraud detection on high-risk transaction types such as CASH_OUT and TRANSFER.
3. Normalize or log-transform transaction amounts to improve model stability.
4. Use balance range and outlier detection as fraud risk indicators.
5. Flag significant balance inconsistencies as anomaly signals.
6. Engineer derived features to enhance fraud detection performance.
7. Focus monitoring efforts on smaller transactions while tracking large transaction anomalies.

---

## 📊 Power BI Dashboard (Coming Soon)

An interactive dashboard will include:

* KPI cards (Total Transactions, Fraud %, Total Amount)
* Fraud distribution visualization
* Transaction type risk analysis
* Amount vs fraud patterns
* Behavioral insights based on balances and ratios

📌 *Dashboard will be updated soon*

---

## 🖼️ Sample Visualizations

```
## 📸 Dashboard Preview

![Fraud Distribution](fraud_distribution.png)
![Transaction Type vs Fraud](type_vs_fraud.png)
![Amount vs Fraud](amount_vs_fraud.png)
![Correlation Heatmap](correlation.png)
```

---

## 🛠️ Tools & Technologies

* Python (Pandas, NumPy)
* Data Visualization (Matplotlib, Seaborn)
* Machine Learning (Scikit-learn)
* Imbalanced Learning (SMOTE)
* Power BI

---

## 🏁 Conclusion

This project demonstrates how **data analysis and machine learning can be combined to solve real-world financial problems**. By integrating EDA, feature engineering, and predictive modeling, the system can effectively detect fraudulent transactions and support data-driven decision-making.

