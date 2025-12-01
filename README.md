# ecommerce-churn-predictions
Machine learning project to predict customer churn using an e-commerce dataset. Includes full EDA, preprocessing, modeling (XGBoost), evaluation, and saved production-ready model.

**Ecommerce Churn Prediction**

Machine learning project to predict customer churn using an e-commerce dataset.
Includes full EDA, preprocessing, feature engineering, modeling (XGBoost), evaluation, and saved production-ready artifacts.

**Project Overview**

Customer churn is a key metric in e-commerce: losing customers means losing recurring revenue.

This project builds a predictive model that identifies users likely to churn so the business can execute proactive retention strategies.

**Main Steps in This Project**

**1. Data Understanding & Cleaning**

**Actions Performed**

Inspected dataset shape and variable types
Identified missing values

Imputed:
Median for numeric features
Mode for categorical features

Removed irrelevant identifiers:
CustomerID

**Purpose**

Ensures the data is complete, consistent, and ready for analysis/modeling.

**2. Exploratory Data Analysis (EDA)**

**Visual & Statistical Analysis**

Distribution plots
Churn proportion analysis
Categorical vs. Churn (countplots)
Numerical vs. Churn (boxplots)
Correlation heatmap
Outlier detection across numeric features

**Key Insights**

Lower tenure customers churn significantly more
Customers who complain have a much higher churn rate
More registered devices & addresses correlate with higher churn

**3. Feature Engineering**

**Transformations Applied**

One-hot encoding of categorical variables
Min-Max scaling of all numerical variables
Removed identifier columns

Final dataset size after encoding: 5630 × 31

**Result**

A fully numeric, model-ready dataset.

**4. Train/Test Split**

80% training (4504 samples)
20% test (1126 samples)

Stratification applied to preserve churn proportion

**5. Model Training & Evaluation**

Six models were trained and compared:

Model	Accuracy	Precision	Recall	F1-score	AUC
XGBoost	0.990	0.973	0.968	0.971	0.9989
Random Forest	0.978	0.988	0.884	0.933	0.998
Decision Tree	0.964	0.890	0.900	0.895	0.938
AdaBoost	0.901	0.784	0.574	0.662	0.917
Logistic Regression	0.794	0.444	0.853	0.584	0.885
Naive Bayes	0.704	0.328	0.716	0.450	0.762

**Best Model: XGBoost**

Highest Recall (critical in churn detection)
Highest F1-score
Near-perfect AUC = 0.999
Very low false negatives
Strong generalization on test data

**6. Model Interpretability**

Top Predictive Features

Tenure (shorter → more churn)
Complain
Order Category – Laptop & Accessory
NumberOfAddress
MaritalStatus_Single
PreferredPaymentMode_E-wallet
NumberOfDeviceRegistered
DaySinceLastOrder

These features help guide business actionability and retention strategy.

**7. Deployment Artifacts**

The project includes saved files ready for production use:

xgboost_churn_model.pkl
scaler.pkl

These can be loaded in any Python environment to make churn predictions on new customers.

**How to Run This Project**

1. Install dependencies
conda env create -f environment.yml
conda activate churn-env

2. Open the notebook
jupyter notebook Project1.ipynb

**Technologies Used**

Python
Pandas / NumPy
Scikit-Learn
XGBoost
Matplotlib / Seaborn
Visual Studio Code
Git & GitHub

**Author**

Leonardo Rodrigues Quintal
