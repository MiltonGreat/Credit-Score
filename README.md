# Credit-Score

### Overview

The goal of this project is to build a machine learning model capable of predicting an individual's creditworthiness based on a variety of features such as age, account balance, job type, education level, and campaign history. The model is trained using Random Forest Classifier, a popular machine learning algorithm, and evaluated using performance metrics such as ROC-AUC and classification report.

### Data Preprocessing

1. Handling Missing Data:
- For numerical columns, missing values were imputed using the median of the column.
- For categorical columns, missing values were imputed using the mode (most frequent value).

2. One-Hot Encoding:
- Categorical features were one-hot encoded to transform them into numerical features.

3. Feature Scaling:
- Numerical features were scaled using StandardScaler to normalize the data before feeding it into the machine learning model.

### Modeling

The machine learning model used for this project is Random Forest Classifier. 

### Evaluation

The performance of the model was evaluated using the following metrics:

- **Classification Report:** Includes precision, recall, F1-score, and support for both classes (0 and 1).
- **ROC-AUC Score:** Measures the model’s ability to distinguish between the two classes.

The model achieved an ROC-AUC Score of 0.9357, indicating that the model is performing well in distinguishing between creditworthy and non-creditworthy individuals.

### Source

https://www.kaggle.com/datasets/parisrohan/credit-score-classification
