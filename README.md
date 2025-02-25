# Creditworthiness Prediction Model

### Overview

This project aims to build a machine learning model to assess the creditworthiness of individuals by predicting their credit scores (e.g., Good, Standard, Bad) based on a dataset containing demographic, financial, and credit history features. The model leverages features such as age, occupation, annual income, outstanding debt, credit mix, and payment behavior to make predictions. The goal is to provide a reliable tool for financial institutions to evaluate credit risk and make informed lending decisions.
#### **Dataset Description**

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

### Modeling

- XGBoost achieved the best performance with 72% accuracy on the validation set.
- Conducted cross-validation to ensure consistency (mean accuracy: 70.64%).

### Results

- **Best Model**: XGBoost achieved the highest accuracy (72%) and balanced precision/recall across classes.

- **Key Insights**:
    - Payment behavior (Payment_of_Min_Amount) and credit history (Credit_Mix) are the most influential features.
    - Financial features like Outstanding_Debt and Interest_Rate also play a significant role.

### Source

https://www.kaggle.com/datasets/parisrohan/credit-score-classification
