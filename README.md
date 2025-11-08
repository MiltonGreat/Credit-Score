# Creditworthiness Prediction Model

### Overview

**A credit score is more than a number; it's a gateway to financial opportunity. An ungoverned model that generates these scores doesn't just assess risk—it allocates opportunity, often unequally.** This project conducts a comprehensive audit of an XGBoost model for creditworthiness prediction, moving beyond accuracy to interrogate its fairness, explainability, and operational risk. While the model achieves 72% accuracy, our audit focuses on a more critical question: Does it perform equitably for all applicants, and can its decisions be explained and defended?

#### Dataset Description

The dataset contains the following types of features:

1. **Demographics**
- **Age**: Age of the individual.
- **Occupation**: Occupation of the individual.
- **Education Level**: Highest level of education completed.

2. **Financial Information**
- **Annual Income**: Yearly income of the individual.
- **Monthly Balance**: Average monthly bank balance.
- **Outstanding Debt**: Total outstanding debt.
- **Credit Utilization Ratio**: Ratio of credit used to total credit available.
- **Num_Credit_Card**: Number of credit cards owned.
- **Num_of_Loan**: Number of active loans.
- **Total_EMI_per_month**: Total monthly EMI payments.

3. **Credit History**
- **Credit_Mix**: Type of credit accounts (e.g., good, bad, standard).
- **Credit_History_Age**: Length of credit history.
- **Delay_from_due_date**: Average number of days delayed in payments.
- **Payment_of_Min_Amount**: Whether the individual pays the minimum amount due (Yes/No).

**Target Variable**
- **Credit_Score**: Categorical variable representing creditworthiness (e.g., Good, Standard, Bad).
  
### Data Preprocessing

1. Handling Missing Data:
- For numerical columns, missing values were imputed using the median of the column.
- For categorical columns, missing values were imputed using the mode (most frequent value).

2. One-Hot Encoding:
- Categorical features were one-hot encoded to transform them into numerical features.

3. Feature Scaling:
- Numerical features were scaled using StandardScaler to normalize the data before feeding it into the machine learning model.

### Approach: The Credit Model Governance Audit

We treated the model development process as a regulatory compliance exercise, with a focus on transparency and fairness.

1. **The Pre-Deployment Bias Audit**

Disparate Impact Analysis: The model's predictions must be audited for fairness across sensitive demographics. Does the rate of "Good" scores differ significantly by age, occupation, or education level when controlling for financial behavior? A model that penalizes a specific profession, even indirectly, poses a clear regulatory risk.

Proxy Variable Interrogation: We scrutinized features like Occupation and Education Level as potential proxies for protected attributes like race or socioeconomic status. Their high feature importance is a red flag demanding rigorous fairness testing.

2. **The Explainability Mandate**

From Black Box to Defensible Decision: The XGBoost model, while accurate, is a complex ensemble. Its deployment is untenable without explainability. We frame the use of SHAP (SHapley Additive exPlanations) as a non-negotiable requirement to answer the critical question: "Why was this applicant given a 'Bad' score?" This allows compliance officers to verify that decisions are based on legitimate factors like Payment_of_Min_Amount and Outstanding_Debt, not bias.

3. **The Feature Importance Reality Check**

Operationalizing Insights: The finding that Payment_of_Min_Amount and Credit_Mix are top features is not just a technical note—it's a strategic insight. It tells the business that these are the most powerful levers for creditworthiness, which should directly inform customer coaching and product design.

### Modeling

- XGBoost achieved the best performance with 72% accuracy on the validation set.
- Conducted cross-validation to ensure consistency (mean accuracy: 70.64%).

### Audit Results & Risk Assessment

- Predictive Power - Accuracy: 72% (XGBoost) MODERATE PASS. The model has reasonable predictive power but leaves significant variance unexplained, requiring cautious deployment with human oversight.
- Model Complexity - XGBoost "Black Box" HIGH RISK without XAI. Deployment is not compliant without SHAP or LIME integration to provide auditable reason codes for every decision.
- Feature Importance - Payment_of_Min_Amount and Occupation are top predictors. REQUIRES INVESTIGATION. The heavy reliance on Occupation necessitates a deep-dive bias audit to ensure it is not acting as a proxy for a protected class.

**Key Governance Finding:** The 72% accuracy score is a double-edged sword. It indicates predictive value but also means the model is wrong 28% of the time. This high error rate, combined with the model's impact on people's lives, mandates a human-in-the-loop system for borderline cases and overturns.

### Conclusion: The Prognosis for Responsible Credit Scoring

This audit demonstrates that building an accurate model is only the first step. Deploying a responsible one requires a governance framework that prioritizes fairness and transparency.

The path to a trustworthy credit scoring AI requires:

1. Mandatory Fairness Testing: Conduct disparate impact analysis prior to any deployment, with clear pass/fail criteria for fairness metrics.

2. Explainability by Design: Integrate SHAP directly into the operational system to provide reason codes for every score, ensuring regulatory defensibility.

3. Continuous Monitoring: Establish a dashboard to track model accuracy and fairness metrics over time, alerting to any drift that could introduce new biases.

### Source

https://www.kaggle.com/datasets/parisrohan/credit-score-classification
