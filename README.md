# homework3
# CSCI 3329 — Homework 3 Report  
**Comparing Classification Algorithms with Feature Selection**

---

## 1. Dataset

- Dataset: Turkish Music Emotion Dataset  
- Source: UCI Machine Learning Repository  
- Samples: 400  
- Features: 50 acoustic features  
- Classes: 4 (emotion categories)

### Class Distribution
(Insert small table or plot if you want bonus points)

---

## 2. Preprocessing

- Removed missing values (none present)
- Dropped irrelevant columns (if any)
- Encoded target labels using LabelEncoder
- Standardized features using StandardScaler

Scaling was necessary due to the use of distance-based models such as KNN and neural networks.

---

## 3. Part 2 — Algorithm Comparison (All Features)

| Algorithm            | Mean Accuracy | Std   |
|---------------------|--------------|-------|
| Linear Classifier   | 0.7619       | 0.0695 |
| Logistic Regression | 0.7906       | 0.0618 |
| KNN                 | 0.7152       | 0.0723 |
| Gaussian NB         | 0.7487       | 0.0718 |
| Neural Network      | 0.7782       | 0.0657 |

---

## 4. Part 3 — Feature Selection

Feature selection was performed using forward selection with Logistic Regression as the base estimator.

Selected features:
- (insert your selected feature list)

| Algorithm            | Mean Accuracy | Std   |
|---------------------|--------------|-------|
| Linear Classifier   | 0.7513       | 0.0748 |
| Logistic Regression | 0.8315       | 0.0670 |
| KNN                 | 0.7318       | 0.0657 |
| Gaussian NB         | 0.7670       | 0.0626 |
| Neural Network      | (your value) | (your value) |

---

## 5. Discussion

Logistic Regression achieved the best overall performance, improving further after feature selection. This suggests that removing redundant acoustic features improved linear separability.

KNN performed poorly due to the high dimensionality of the dataset, which reduces the effectiveness of distance-based methods.

Gaussian Naive Bayes improved slightly after feature selection due to reduced feature dependency violations.

Neural networks showed stable performance, indicating moderate non-linear structure in the dataset.

Overall, feature selection improved model efficiency and performance for most algorithms.

---

## 6. Reproducibility

- Python version: 3.x  
- Libraries: scikit-learn, pandas, numpy  
- Random state: 42 and 17342  
- Evaluation: RepeatedKFold (10 folds, repeated 10 times)

To run:

```bash
pip install -r requirements.txt
jupyter notebook
