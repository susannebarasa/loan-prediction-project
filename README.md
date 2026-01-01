# Loan Prediction Project  
*Kaggle Case Study*

A) Project Overview

This project focuses on predicting whether a loan application should be **approved (Y)** or **rejected (N)** using applicant demographic and financial data.  
Beyond model accuracy, the project emphasizes **business validation**, particularly how different decision thresholds impact **risk vs. loan approvals**—a critical consideration for financial institutions.

---

B) Objective

To build and evaluate machine learning models that predict loan approval outcomes while balancing:
- Approval rates  
- Default risk  
- Business priorities of a lending institution  

---

C) Dataset

The dataset is sourced from a Kaggle loan prediction case study and includes features such as:
- Applicant income  
- Co-applicant income  
- Loan amount  
- Credit history  
- Education, marital status, dependents  
- Property area  

**Target Variable:** `Loan_Status` (Y / N)

---

D) 🧩 Project Structure

loan-prediction-project/
├── data/
│ └── loan_data.csv
├── notebooks/
│ └── loan_status.ipynb
├── requirements.txt
└── README.md


---

E)  Methodology

 1️⃣ Exploratory Data Analysis (EDA)
- Visualized categorical and numerical features  
- Examined distributions and class imbalance  
- Checked correlations and feature relationships  

 2️⃣ Data Preprocessing
- Handled missing values  
- Applied one-hot encoding to categorical variables  
- Ensured feature alignment between training and test datasets  

 3️⃣ Modeling
The following models were trained and evaluated:
- **Logistic Regression** (baseline model)  
- **Random Forest**  
- **XGBoost**  

 4️⃣ Hyperparameter & Threshold Tuning
- Used **GridSearchCV** for hyperparameter tuning  
- Adjusted classification thresholds to evaluate business trade-offs between:
  - Recall (loan approvals)  
  - Precision (risk control)  

---

F) Model Performance Summary

| Model | Accuracy | Notes |
|------|----------|------|
| Logistic Regression | ~85% | Strong and interpretable baseline |
| Random Forest | ~84% | Balanced performance |
| Tuned XGBoost (0.5) | ~82% | Best suited for business threshold tuning |

---

 Business Validation (Key Insight)

Rather than relying solely on accuracy, this project evaluates **decision thresholds** to reflect real-world banking priorities.

 🔹 Threshold = 0.4
- **Recall ≈ 97%**  
- Approves almost all eligible loans  
- Higher risk due to more false approvals  
- Suitable for **aggressive lending strategies**

 🔹 Threshold = 0.6
- Higher **precision**  
- Fewer risky approvals  
- Lower total approvals  
- Safer option for **risk-averse banks**

---

G)  Final Recommendation

👉 **Threshold = 0.6** is recommended for business use  
- Prioritizes minimizing loan defaults  
- Aligns with conservative banking risk policies  

👉 **Threshold = 0.4** may be used when growth and market expansion are prioritized over risk control  

---

H) Key Takeaways

- Accuracy alone is insufficient for financial decision-making  
- Threshold tuning is essential in risk-sensitive domains  
- Business context should guide model evaluation, not metrics alone  

---

I) How to Run the Project

```bash
git clone https://github.com/susannebarasa/loan-prediction-project.git
cd loan-prediction-project
pip install -r requirements.txt
jupyter notebook notebooks/loan_status.ipynb