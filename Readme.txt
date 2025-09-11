📌 Loan Prediction Project (Kaggle Case Study)

Objective:
Predict whether a loan should be approved (Y) or not (N) using applicant data.

Steps Taken:

EDA – Visualized categorical and numerical features, checked correlations.

Preprocessing – Handled missing values, one-hot encoding, feature alignment.

Models Tried – Logistic Regression, Random Forest, XGBoost.

Tuning – Hyperparameter tuning with GridSearchCV, threshold tuning.

Business Validation – Evaluated trade-offs between approvals and risk.

Key Results:

Logistic Regression: ~85% accuracy (good baseline).

Random Forest: balanced performance (~84%).

Tuned XGBoost: 82% accuracy @ threshold 0.5.

XGBoost with threshold 0.4 → Recall ↑ (97%), more approvals but riskier.

XGBoost with threshold 0.6 → Precision ↑ (fewer risky approvals), fewer loans approved.

📊 Business Validation

Banks value risk minimization more than just approvals.

Threshold = 0.4:

High recall (97%) → Approves almost all good loans, but lets in more risky loans.

Threshold = 0.6:

Higher precision → Fewer false approvals (bad loans), safer for the bank.

Decision:
👉 Recommend threshold = 0.6 for business use (prioritizes minimizing defaults).
👉 Threshold = 0.4 can be used if the bank wants aggressive lending (higher approvals).