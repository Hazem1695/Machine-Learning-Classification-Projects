---

# Bank Customer Churn Prediction — Machine Learning Experiments

## Project Overview

This repository contains a complete end-to-end machine learning experimentation workflow for solving an imbalanced classification problem using the **Bank Customer Churn Dataset**.

The primary goal of this project is to identify customers who are likely to leave the bank (churn) by comparing and evaluating multiple machine learning algorithms under different preprocessing and imbalance-handling strategies.

The project focuses heavily on:

* Model experimentation
* Imbalanced classification handling
* Performance evaluation
* Hyperparameter tuning
* Comparative analysis
* Model selection based on business-oriented metrics

---

# Problem Statement

Customer churn is one of the most critical business problems in the banking industry. Retaining existing customers is significantly less expensive than acquiring new ones.

The objective of this project is to build machine learning models capable of predicting whether a customer will leave the bank based on customer-related features.

This is treated as a **binary classification problem**:

* `0` → Customer stays
* `1` → Customer leaves (churn)

---

## Model Release Schedule
To maintain consistency and focus on understanding each model deeply, this project is structured as a daily release series, where each model is implemented, analyzed, and published separately.

| Day    | Model Name                                    | Publish Date    | Status      |
| ------ | --------------------------------------------  | --------------- | ----------- |
| 1      | Logistic Regression Classification            | 2026-05-8       | Completed   |
| 2      | K-Nearest Neighbors (KNN) Classification      | 2026-05-9       | Completed   |
| 3      | Support Vector Machine (SVM) Classification   | 2026-05-12      | Completed   |
| 4      | Naive Bayes Classification                    | 2026-05-13      | Completed   |
| 5      | Decision Trees Classification                 | 2026-05-14      | Completed   |
| 6      | Random Forest Classification                  | 2026-05-15      | Completed   |

- In Progress – Currently being worked on
- Planned – Not uploaded yet
- Completed – Uploaded and documented
- TBD – To Be Determined

---

# Project Goals

The main goals of this project are:

* Build multiple classification models from scratch
* Compare different machine learning algorithms
* Handle imbalanced data effectively
* Experiment with multiple preprocessing techniques
* Evaluate models using appropriate metrics for imbalanced classification
* Identify the best-performing model for deployment
* Understand how preprocessing affects different algorithms
* Improve recall and ROC-AUC performance for churn prediction

---

# Machine Learning Models Implemented

The following models were implemented and evaluated:

1. Logistic Regression
2. K-Nearest Neighbors
3. Support Vector Machine
4. Gaussian Naive Bayes
5. Decision Tree Classifier
6. Random Forest Classifier

---

# Experiments Conducted

Each notebook contains detailed experiments including:

* Data preprocessing
* Feature scaling
* Handling categorical variables
* Imbalanced data handling
* Model training
* Cross-validation
* Hyperparameter tuning
* Performance comparison
* Confusion matrix analysis
* Classification report analysis
* ROC-AUC evaluation

---

# Data Preprocessing Techniques

The following preprocessing techniques were explored throughout the experiments:

## Feature Scaling

* StandardScaler
* RobustScaler

## Encoding Techniques

* One-Hot Encoding
* One-Hot Encoding with `drop='first'`

## Imbalanced Data Handling

* SMOTE (Synthetic Minority Oversampling Technique)
* `class_weight='balanced'`

---

# Evaluation Metrics

Since the dataset is imbalanced, accuracy alone was not used as the primary evaluation metric.

The following metrics were used for evaluation:

* Accuracy Score
* Precision
* Recall
* F1-Score
* ROC-AUC Score
* Cross-Validation Mean Accuracy
* Standard Deviation

Special attention was given to:

* Recall for the minority class
* ROC-AUC Score
* Generalization capability

---

# Key Findings and Insights

## Logistic Regression

* Performed well as a baseline model
* `class_weight='balanced'` significantly improved minority class recall
* Stable and interpretable model

## K-Nearest Neighbors

* Performance improved when scaling was applied before SMOTE
* Sensitive to feature scaling
* StandardScaler performed better than RobustScaler

## Support Vector Machine

* Radial Basis Function kernel achieved the best Support Vector Machine performance
* Strong separation capability on nonlinear patterns
* One of the strongest models in the project

## Gaussian Naive Bayes

* Struggled with the dataset due to feature dependency assumptions
* Performance improved after applying encoding and imbalance handling
* Not suitable as the final deployment model

## Decision Tree

* Hyperparameter tuning significantly improved performance
* Achieved very strong recall scores
* Demonstrated the importance of overfitting control

## Random Forest

* Achieved the best overall performance
* Provided the best balance between recall and ROC-AUC
* Demonstrated strong generalization capability
* Selected as the final recommended model

---

# Best Performing Model

## Final Selected Model

### Random Forest Classifier

### Best Configuration

```python
RandomForestClassifier(
    n_estimators=200,
    max_depth=10,
    min_samples_leaf=3,
    min_samples_split=10,
    max_features='sqrt',
    criterion='entropy',
    random_state=0
)
```

---

# Final Model Performance

| Metric                 | Score |
| ---------------------- | ----- |
| Accuracy               | 0.828 |
| ROC-AUC Score          | 0.785 |
| Recall (Churn Class)   | 0.71  |
| F1-Score (Churn Class) | 0.63  |

---

# Important Technical Insights

## Imbalanced Classification

This project demonstrated that:

* Accuracy can be misleading in imbalanced datasets
* Recall and ROC-AUC are more informative metrics
* Imbalance handling techniques significantly affect model behavior

---

## Scaling Effects

The experiments showed that:

* Distance-based algorithms heavily depend on scaling
* Tree-based models are mostly unaffected by scaling
* StandardScaler consistently performed well across multiple models

---

## Hyperparameter Tuning

Hyperparameter tuning significantly improved:

* Decision Tree performance
* Random Forest generalization
* Minority class detection capability

---

# Technologies Used

## Programming Language

* Python

## Libraries

* NumPy
* Pandas
* Scikit-learn
* Imbalanced-learn

---

# Future Improvements

Potential future enhancements include:

* XGBoost implementation
* LightGBM implementation
* CatBoost implementation
* Ensemble learning techniques
* Threshold tuning
* Precision-Recall optimization

---

# Conclusion

This project provides a comprehensive practical study of machine learning classification techniques for customer churn prediction.

The experiments highlight:

* The importance of proper preprocessing
* The impact of imbalance handling
* The strengths and weaknesses of different algorithms
* The importance of evaluation metric selection

After extensive experimentation, the Random Forest model achieved the strongest overall performance and was selected as the final recommended model for deployment.

---

# Author

## Hazem Mohamed

Artificial Intelligence Engineer | Machine Learning Engineer

* Passionate about Artificial Intelligence, Machine Learning, Deep Learning, and Large Language Models
* Focused on building real-world end-to-end machine learning systems
* Interested in applied Artificial Intelligence research and education

