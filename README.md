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

- The model is highly effective at predicting the False class but struggles significantly with the True class, as indicated by lower precision, recall, and F1-score.

- The imbalance in class performance suggests the model is biased toward the False class, likely due to class imbalance in the dataset (5580 False vs. 716 True).

- While the ROC-AUC score is high (0.9357), the model's utility depends on the importance of correctly identifying True cases. For tasks where identifying the True class is critical (e.g., fraud detection or medical diagnosis), this model might need further improvement. 

### Source

https://www.kaggle.com/datasets/parisrohan/credit-score-classification
