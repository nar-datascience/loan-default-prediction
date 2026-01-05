[README-loan-default-prediction.md](https://github.com/user-attachments/files/24441423/README-loan-default-prediction.md)
# Credit Risk and Loan Default Prediction

## Project Overview
This project predicts the probability of loan default at origination using historical Lending Club data. A feedforward neural network was developed with strict data leakage controls and interpreted using SHAP to identify the key drivers of credit risk. The model achieves strong discriminatory performance while maintaining interpretability suitable for real-world credit decisioning.

---

## Business Problem
Financial institutions must balance loan approval rates with default exposure. Misclassifying high-risk borrowers can lead to significant financial losses, while overly conservative screening reduces revenue. 

The goal of this project is:

1. To identify high-risk borrowers early using only information available at the time of loan approval.
2. To determine the strongest predictors of default risk.

---

## Data Description

- **Source:** Kaggle - Lending Club Loan Data - https://www.kaggle.com/datasets/adarshsng/lending-club-loan-data-csv
- **Loans:** over 2.2 million
- **Time Period:** 2007-2015
- **Target Variable:** Loan status - encoded to be binary
- **Features:** 145 before feature engineering

Features include borrower financial attributes, credit profile metrics, and loan characteristics.

---

## Methodology

**Preprocessing:**

- Binary encode target variable
- Feature-specific missing value imputation
- Yeo-Johnson transformation for skewed variables
- Standardization and one-hot encoding

**Modeling:**

- Feedforward neural network implemented in Keras
- Binary cross-entropy loss with Adam optimizer
- Regularization via dropout and early stopping

**Evaluation:**

- ROC-AUC and recall prioritized due to higher cost of false negatives
- Tuned prediction threshold based on optimal recall-precision tradeoff

**Interpretability:**

- SHAP used to explain global feature importance and nonlinear interactions

---

## Key Insights

- Recent credit inquiries are the strongest predictor of default risk
- Loan sub-grade significantly influences default probability
- Interest rate amplifies risk, particularly when combined with frequent inquiries
- Higher income and revolving credit limits reduce default risk
- Joint applications and verified income are associated with lower risk


---

## Recommendations

- Flag applicants with high inquiry volume and poor sub-grades for additional review
- Incorporate nonlinear risk interactions into underwriting decisions
- Use model outputs as a risk-scoring or pre-screening tool, rather than a strict approval cutoff

---

## Tools & Technologies
- **Python**
- **pandas**, **NumPy** – data manipulation  
- **matplotlib** – visualization  
- **Keras** – deep learning, feedforward neural network 
- **Jupyter Notebook** – analysis and documentation  

---

## Repository Structure
```
├── Credit Risk and Loan Default Prediction Report.pdf
├── Credit Risk and Loan Default Prediction.html
├── Credit Risk and Loan Default Prediction.ipynb
├── README.md
```

---

## Next Steps
- Benchmark against logistic regression and gradient boosting models
- Conduct fairness and bias analysis across demographic proxies
- Perform temporal validation to assess model stability across economic cycles

---

## Contact
If you’d like to discuss this project or explore related work, feel free to connect with me on LinkedIn or view my other repositories.
