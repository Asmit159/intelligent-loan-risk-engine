# 🏦 Intelligent Loan Risk, Interest Rate & EMI Optimization System  
**End-to-End Machine Learning Project (Logistic Regression + Business Logic)**

---

## 📌 Overview

This project implements a **real-world loan decision system** inspired by how banks and fintech companies actually operate.

Instead of treating loan approval as a simple yes/no prediction, the system:

- Predicts **loan approval probability** using classical ML  
- Converts probability into a **risk score**
- Uses **transparent business rules** to decide:
  - Interest rate
  - EMI options under affordability constraints

The system is intentionally built using **logistic regression**, with a strong focus on **interpretability, safety, and business realism**.

---

## 🎯 Problem Statement

Banks must balance:
- **Risk control** (avoiding defaults)
- **Customer affordability** (fair EMIs and pricing)

Pure rule-based systems are rigid, while black-box ML models are hard to audit.

### Goal:
> Use ML to **estimate risk**, and business logic to **make financial decisions** that are explainable and safe.

---

## 🛠 Tech Stack & Tools
<p style="text-align:=centre:">
  
### 🔹 Languages
![Python](https://img.shields.io/badge/Python-3.9+-3776AB?style=for-the-badge&logo=python&logoColor=white)



### 🔹 Machine Learning & Data
![Logistic Regression](https://img.shields.io/badge/Logistic%20Regression-Classical%20ML-0A66C2?style=for-the-badge)
![NumPy](https://img.shields.io/badge/NumPy-Scientific%20Computing-013243?style=for-the-badge&logo=numpy&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=for-the-badge&logo=pandas&logoColor=white)



### 🔹 Modeling Concepts
![Supervised Learning](https://img.shields.io/badge/Supervised%20Learning-Core%20ML-6A5ACD?style=for-the-badge)
![Feature Engineering](https://img.shields.io/badge/Feature%20Engineering-Business%20Driven-228B22?style=for-the-badge)
![Bias Variance](https://img.shields.io/badge/Bias--Variance%20Analysis-Model%20Evaluation-B22222?style=for-the-badge)
![Probability Modeling](https://img.shields.io/badge/Probabilistic%20Modeling-Explainable%20ML-4682B4?style=for-the-badge)

</p>

---

## 🧠 Design Philosophy

- ML predicts **risk**, not prices  
- Pricing and EMIs are decided via **business rules**
- Simplicity > complexity  
- Explainability > black-box accuracy  

This mirrors real **regulated lending systems**.

---

## 🗂 Dataset
- Check it out in data folder
- Public, bank-style loan dataset  
- Each row represents one applicant  
- Target: **loan approval status**

### Key Inputs
- Loan amount  
- Annual income  
- Number of dependents  
- Employment type (self-employed / salaried)  
- CIBIL score  
- Asset values (bank, residential, commercial, luxury)

---

## 🔍 Key Data Insights

- **CIBIL score is the dominant approval factor**
- Applicants with **CIBIL > ~550** are mostly approved
- **Exceptions exist** where low-CIBIL applicants are approved due to:
  - High income
  - Strong asset backing
  - Employment stability

This confirms that loan decisions are **multi-factor**, not threshold-based.

---

## ⚙️ Feature Engineering Highlights

- **Liquidity-aware total assets**  
  (bank assets weighted higher than property and luxury assets)

- **Loan-to-Income Ratio**  
  Captures repayment stress better than raw values

- **Asset-to-Loan Coverage Ratio**  
  Measures collateral strength and downside protection

These features reflect **real underwriting logic**.

---

## 🤖 Machine Learning Model

- **Model:** Logistic Regression  
- **Why:**  
  - Probabilistic output (0–1)  
  - Interpretable coefficients  
  - Industry-preferred in finance  
  - Direct alignment with Andrew Ng’s ML foundations  

The model outputs an **approval probability**, not a hard decision.

---

## ⚖️ Risk Scoring & Interest Rate Logic (High-Level)

- Approval probability → **Risk Score = 1 − P**
- Risk scores are mapped into **stable risk buckets**
- Interest rates are assigned via **business rules**, not ML

| Risk Category | Interest Rate |
|--------------|---------------|
| Very Low Risk | 8.0% |
| Low Risk | 9.5% |
| Medium Risk | 11.5% |
| High Risk | 14.5% |
| Very High Risk | Reject / 16% |

Guardrails:
- Minimum rate: 8.0%  
- Maximum rate: 16.0%  
- Automatic rejection at extreme risk  

---

## 📊 EMI Optimization (High-Level)

- EMI calculated using standard banking formula  
- Multiple tenures evaluated (12–60 months)
- **Affordability constraint enforced**
---
## 🧪 Extensions & Future Work

- REST API using Spring Boot
- Interactive UI using Streamlit / React
- Model explainability dashboard
- Integration with real credit bureau data
- Separate regression model for loss estimation
