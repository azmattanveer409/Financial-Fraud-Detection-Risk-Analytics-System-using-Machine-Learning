# 📊 🚨 Financial Fraud Detection & Risk Analytics System using Machine Learning

## 🚀 Overview

This project focuses on detecting fraudulent financial transactions using **data analysis, feature engineering, and machine learning techniques**. The objective is to identify suspicious transaction patterns and build a predictive system that classifies transactions as **fraudulent or legitimate**.

The project combines **Exploratory Data Analysis (EDA)**, **feature engineering**, and **machine learning models**, along with a **Power BI dashboard** for interactive insights.

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

## 📸 Chart Visualizations

### 1. Fraud Distribution
![Fraud Distribution](images/fraud_distribution.png)

> Shows the proportion of fraudulent vs legitimate transactions. Fraud cases represent only **0.13%** of all transactions — confirming extreme class imbalance that must be handled before model training using techniques like SMOTE or class weighting.

---

### 2. Transaction Type vs Fraud
![Transaction Type vs Fraud](images/transaction_type_vs_fraud.png)

> Breaks down fraud occurrence by transaction category. **CASH_OUT** and **TRANSFER** are the only types where fraud appears — making them the two highest-risk categories and the primary focus for any fraud detection pipeline.

---

### 3. Amount vs Fraud
![Amount vs Fraud](images/amount_vs_fraud.png)

> Compares transaction amount distributions for fraudulent vs legitimate cases. Fraud is concentrated in **mid-to-low value ranges**, suggesting fraudsters deliberately avoid high-value transactions to evade rule-based detection thresholds.

---

### 4. Correlation Heatmap
![Correlation Heatmap](https://github.com/azmattanveer409/Financial-Fraud-Detection-Risk-Analytics-System-using-Machine-Learning/blob/e638d0262ae6e16ff2566a3e9e00678440450f9f/Fraud%20Detection(1).png)

> Displays pairwise correlations between all numerical features. Strong relationships exist between **balance columns and transaction amounts**, while engineered error features show stronger links to the fraud label than the raw balance fields alone — validating the feature engineering approach.

---

## 💼 Power BI Dashboard

An interactive **3-page Power BI dashboard** was built to visualize fraud patterns, transaction behavior, and detection performance at scale across 6.36 million transactions.

---

### Page 1 — Fraud Overview & Financial Risk Monitoring
![Page 1 - Fraud Overview](https://github.com/azmattanveer409/Financial-Fraud-Detection-Risk-Analytics-System-using-Machine-Learning/blob/e638d0262ae6e16ff2566a3e9e00678440450f9f/Fraud%20Detection(1).png)

> High-level fraud KPIs across **6.36M transactions** totalling **$1 Trillion**. Confirmed fraud stands at **8,213 cases** with a **12.91% fraud rate** and **$12.06 Billion** in estimated losses. Features fraud trend over time, fraud distribution by type, and transaction volume breakdown — CASH_OUT and PAYMENT emerge as dominant fraud channels.

---

### Page 2 — Transaction Behavior & Balance Analysis
![Page 2 - Transaction Behavior](dashboard/page2_transaction_behavior.png)

> Deep-dive into balance flows and financial anomalies. Tracks avg transaction value (**$180K**), avg origin balance (**$833.88K**), net balance change (**$855.11K**), and balance error exposure (**-$201.09K**). Includes amount trend spikes up to $6.2M, balance movement scatter, and error pattern analysis — TRANSFER transactions carry an **87.80% positive error rate**.

---

### Page 3 — Fraud Detection Performance & Risk Profiling
![Page 3 - Detection Performance](dashboard/page3_detection_performance.png)

> Evaluates the system's detection capability at a **19.48% detection rate**. Fraud risk classification shows CASH_OUT (4,116 cases / $394B) and TRANSFER (4,097 cases / $485B) as the primary risk vectors. Includes high-risk account identification, risk exposure scatter, and actual vs flagged fraud gap analysis.

---

## 🤖 Machine Learning Approach

### 🔹 Problem Type
**Supervised Learning → Binary Classification**

### 🔹 Models Used
* **Logistic Regression** — Baseline model
* **Random Forest** — Advanced ensemble model

### 🔹 Data Handling
* Train-test split: **80% training / 20% testing**
* **SMOTE** applied to address class imbalance

---

## 📈 Model Evaluation

| Metric | Description |
|--------|-------------|
| **Confusion Matrix** | Measures correct and incorrect predictions |
| **Precision** | Accuracy of fraud predictions |
| **Recall** ⚠️ | Ability to detect actual fraud cases *(critical metric)* |
| **F1-Score** | Balance between precision and recall |
| **ROC-AUC Score** | Overall model discrimination performance |

👉 The **Random Forest model** demonstrated strong performance in identifying fraud patterns across highly imbalanced data.

---

## 🔍 Key Insights

1. Fraud cases are extremely rare — **0.13%** of total transactions (severe class imbalance)
2. **100% of fraud** is concentrated in CASH_OUT and TRANSFER transaction types
3. Fraud is **more common in lower-value transactions**, not large ones
4. Fraudulent transactions are associated with **abnormal balance variations**
5. Large deviations in balance errors are reliable **anomaly detection signals**
6. Strong correlations between balances and amounts — engineered features improve detection
7. Smaller transactions require **more focused monitoring** than large ones

---

## 🚀 Strategic Recommendations

1. Apply SMOTE or class-weighted metrics to handle class imbalance effectively
2. Prioritize fraud detection on **CASH_OUT** and **TRANSFER** transaction types
3. Log-transform transaction amounts to reduce skewness and improve model stability
4. Use balance range and outlier flags as **fraud risk indicators**
5. Flag significant balance inconsistencies in real-time pipelines
6. Leverage engineered features (errorOrig, errorDest) as primary fraud signals
7. Focus monitoring on **smaller transactions** while separately tracking large anomalies

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|------|---------|
| **Python** (Pandas, NumPy) | Data manipulation and preprocessing |
| **Matplotlib, Seaborn** | EDA visualizations |
| **Scikit-learn** | Machine learning models and evaluation |
| **Imbalanced-learn (SMOTE)** | Class imbalance handling |
| **Power BI** | Interactive business intelligence dashboard |

---

## 📁 Project Structure

```
Financial-Fraud-Detection/
│
├── notebook/
│   └── fraud_detection.ipynb          # Main analysis notebook
│
├── data/
│   └── fraud_dataset.csv              # Transaction dataset
│
├── images/                            # EDA chart exports
│   ├── fraud_distribution.png
│   ├── transaction_type_vs_fraud.png
│   ├── amount_vs_fraud.png
│   └── correlation_heatmap.png
│
├── dashboard/                         # Power BI dashboard screenshots
│   ├── page1_fraud_overview.png
│   ├── page2_transaction_behavior.png
│   └── page3_detection_performance.png
│
├── Fraud Detection System.pbix        # Power BI report file
└── README.md
```

---

## 🏁 Conclusion

This project demonstrates how **data analysis and machine learning can be combined to solve real-world financial problems**. By integrating EDA, feature engineering, predictive modeling, and an interactive Power BI dashboard, the system can effectively detect fraudulent transactions and support **data-driven decision-making** in financial risk management.

---

## 👤 Author

**Azmat Tanveer**  
🔗 [GitHub Profile](https://github.com/azmattanveer409)

---

> ⭐ If you found this project useful, please consider giving it a star on GitHub!
