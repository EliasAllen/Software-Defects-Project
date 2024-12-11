# Software Defects Prediction Challenge

This repository holds an attempt to predict software defects using a binary classification dataset derived from the Software Defect Dataset. The work was completed as part of a Kaggle-style competition.

---

## Overview

The task is to predict the probability of software defects (`True`) based on a dataset of software metrics. The dataset consists of features like code complexity, branch counts, and other measurable properties of the code. Our approach formulates this problem as a binary classification task using a Random Forest model.

Key Results:
- **Accuracy**: 80.68%
- **ROC-AUC**: 77.15%
- The model effectively distinguishes between defective and non-defective code, though improvements are possible for the minority class.

---

## Summary of Work Done

### Data

**Dataset Description**:
- **Source**: The dataset is a modified version of the Software Defect Dataset.
- **Input**: Numerical and integer features describing software metrics.
- **Target**: Binary flag indicating the presence of defects (`True` or `False`).

**Instances**:
- **Training Data**: 101,763 samples
- **Test Data**: 67,842 samples
- **Validation Split**: 71,234 (train), 15,264 (validation), 15,265 (test)

**Preprocessing**:
- Identified and capped outliers in key features (`loc`, `branchCount`, `v(g)`, `ev(g)`, `n`).
- Standardized numerical features to ensure equal weight across the model.

**Data Visualization**:
- Histogram plots and boxplots were used to analyze feature distributions.
- Key correlated features with the target include `loc`, `branchCount`, and `v(g)`.

---

### Problem Formulation

**Input**: A set of numerical features describing software metrics.

**Output**: Probability of software defects (`True`).

**Model**:
- **Random Forest Classifier**: Selected for its robustness and ability to handle imbalanced datasets.

**Hyperparameters**:
- `n_estimators`: 100
- `class_weight`: Balanced to address class imbalance.

---

### Training

**Training Setup**:
- **Environment**: JupyterLab
- **Hardware**: Standard laptop with limited computational resources.
- **Software**: Python, Scikit-learn, Matplotlib, Pandas.

**Training Details**:
- Training split into 70% train, 15% validation, and 15% test.
- Model performance tracked via accuracy and ROC-AUC metrics.

**Challenges**:
- Addressing class imbalance in the target variable.
- Managing outliers effectively.

**Results**:
- **Accuracy**: 80.68%
- **ROC-AUC**: 77.15%

---

### Performance Comparison

| Metric        | Validation Set |
|---------------|----------------|
| Accuracy      | 80.68%         |
| ROC-AUC       | 77.15%         |
| Precision (True) | 64%          |
| Recall (True)   | 34%           |

![ROC Curve](path/to/roc_curve_image.png) *(Replace with actual path)*

---

### Conclusions

- Features like `loc` and `branchCount` are key predictors of software defects.
- Class imbalance affects recall for the minority class, and further techniques like SMOTE could improve performance.
- Random Forest is an effective baseline model for this task.

---

### Future Work

- Implement techniques to address class imbalance, such as oversampling or SMOTE.
- Experiment with additional models like Gradient Boosting or Neural Networks.
- Evaluate the impact of feature engineering or domain-specific transformations.

---

## How to Reproduce Results

### Software Setup

**Required Packages**:
- Python 3.8+
- Pandas
- Matplotlib
- Scikit-learn
- Seaborn

Install packages using:
```bash
pip install -r requirements.txt
