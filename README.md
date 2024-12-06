
# Customer Churn Prediction

This repository contains a machine learning pipeline to predict customer churn for a telecommunications company. Customer churn refers to the scenario where customers stop using a company's services. The project aims to predict whether a customer will churn based on various features, enabling the company to take proactive measures to retain customers.

---

## Table of Contents
1. [Project Overview](#project-overview)
2. [Dataset](#dataset)
3. [Steps and Workflow](#steps-and-workflow)
4. [Model Performance](#model-performance)
5. [Insights and Recommendations](#insights-and-recommendations)
6. [How to Run](#how-to-run)
7. [Requirements](#requirements)
8. [Acknowledgements](#acknowledgements)

---

## Project Overview

This project applies a machine learning pipeline to predict customer churn and provide actionable insights. Key tasks include:
- Data preprocessing: cleaning and encoding features.
- Model training and evaluation.
- Deriving actionable business insights from model results.

---

## Dataset

The dataset contains the following categories of features:
- **Demographic Data**: Gender, senior citizen status, and dependent status.
- **Account Data**: Contract type, payment method, tenure, and monthly/total charges.
- **Service Data**: Internet service, online security, tech support, and streaming services.

The target variable is `Churn`, indicating whether the customer churned.

---

## Steps and Workflow

### 1. Data Preprocessing
- Filled missing values in `TotalCharges` with the median value.
- Encoded binary categorical columns (`Yes/No`) into numeric values (`1/0`).
- One-hot encoded multi-class categorical variables (e.g., `InternetService`, `Contract`).
- Scaled continuous numerical features using `StandardScaler`.

### 2. Model Training
- A Random Forest Classifier was used to train the model, leveraging its ability to handle mixed data types and its feature importance insights.

### 3. Model Evaluation
- The model was evaluated using metrics like precision, recall, F1-score, accuracy, and ROC-AUC.
- Confusion matrix and feature importance plots were generated to interpret results.

### 4. Insights and Recommendations
- Feature importance scores were analyzed to understand the drivers of churn.
- Business strategies were proposed to reduce churn based on model insights.

---

## Model Performance

### Key Metrics:
- **Accuracy**: 79%
- **Precision (Churners)**: 0.64
- **Recall (Churners)**: 0.44
- **ROC-AUC Score**: 0.832

### Confusion Matrix:
|                 | Predicted Non-Churn | Predicted Churn |
|-----------------|----------------------|-----------------|
| **Actual Non-Churn** | 1036                 | 91              |
| **Actual Churn**     | 190                  | 183             |

---

## Insights and Recommendations

### Key Insights:
- Customers with short tenure and high monthly charges are more likely to churn.
- `tenure`, `MonthlyCharges`, and `TotalCharges` are significant predictors of churn.

### Recommendations:
1. **Retention Offers**: Provide discounts or retention offers to customers at risk of churning, especially those with short tenure or high charges.
2. **Service Improvement**: Enhance customer support for fiber optic internet users, as they exhibit a higher likelihood of churn.
3. **Targeted Marketing**: Focus marketing efforts on at-risk customers to improve satisfaction and retention.

---

## How to Run

1. Clone this repository:
   ```bash
   git clone <repository-url>
   cd <repository-folder>
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Run the Python script to train and evaluate the model:
   ```bash
   python churn_prediction.py
   ```

---

## Requirements
- Python 3.8+
- Libraries:
  - pandas
  - numpy
  - scikit-learn
  - matplotlib
  - seaborn

---

## Acknowledgements
This project is inspired by real-world telecommunications challenges. Special thanks to the open-source community for providing tools and libraries that made this analysis possible.

