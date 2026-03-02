# Customer Churn Prediction

## Problem Statement
This project aims to predict whether a customer will churn (leave the service) using the Telco Customer Churn dataset. Early identification of churners helps businesses apply retention strategies and reduce revenue loss.

## Dataset
The dataset contains customer demographic information, account details, service usage, and billing information. The target variable is `Churn`.

## Data Preprocessing
- Handled missing values
- Converted categorical variables using one-hot encoding
- Addressed class imbalance using class weights
- Split data into training and testing sets

## Model Used
RandomForestClassifier with:
- n_estimators = 300
- max_depth = 8
- min_samples_leaf = 5
- class_weight = "balanced"

## Evaluation Metrics
Since missing churners is more costly than false positives, recall for the churn class was prioritized over raw accuracy.

### Test Performance:
- Recall (Churn): ~0.81
- Precision (Churn): ~0.47
- Accuracy: ~0.70

### Cross-Validation:
- Mean Recall: ~0.83
- Standard Deviation: ~0.02

Low variance across folds indicates stable model performance.

## Business Interpretation
The model captures the majority of churners while accepting a moderate number of false positives. This tradeoff is appropriate when customer retention value outweighs marketing outreach cost.

## Future Improvements
- Probability threshold tuning
- Feature importance analysis
- Model deployment via API
- Hyperparameter optimization
