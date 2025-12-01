# ecommerce-churn-predictions
Machine learning project to predict customer churn using an e-commerce dataset. Includes full EDA, preprocessing, modeling (XGBoost), evaluation, and saved production-ready model.

**Ecommerce Churn Prediction**

Predicting customer churn using machine learning on an e-commerce dataset.
This project includes full EDA, preprocessing, feature engineering, model training, evaluation, and deployment artifacts.

**Project Overview**

Customer churn is a critical KPI in e-commerce.
The goal of this project is to build a predictive model that identifies customers who are likely to stop using the platform.

This enables businesses to create targeted retention strategies and reduce revenue loss.

**Main Steps in This Project**
**Data Understanding & Cleaning**

Checked dataset shape and variable types

Identified missing values

Imputed:

Median for numeric features
Mode for categorical features
Removed irrelevant identifiers (e.g., CustomerID)

**Exploratory Data Analysis (EDA)**

Performed extensive visual and statistical analysis:
Churn distribution
Categorical vs Churn visualizations
Numerical vs Churn boxplots
Correlation heatmap
Outlier detection via boxplots

Key insights:

Customers with low tenure churn more.
Customers who complained churn significantly more.
Higher number of devices and address count increase churn probability.

**Feature Engineering**

One-hot encoding of all categorical variables
Min-Max scaling on numerical features
Final dataset after encoding: 5630 rows × 31 columns

**Train/Test Split**

80% training, 20% testing
Stratified split to preserve churn ratio
Training set: 4504 samples
Test set: 1126 samples

**Model Training & Evaluation**

Trained multiple classification models:

Model	Accuracy	Precision	Recall	F1-score	AUC
XGBoost	0.990	0.973	0.968	0.971	0.9989
Random Forest	0.978	0.988	0.884	0.933	0.998
Decision Tree	0.964	0.890	0.900	0.895	0.938
AdaBoost	0.901	0.784	0.573	0.662	0.917
Logistic Regression	0.794	0.443	0.852	0.583	0.885
Naive Bayes	0.704	0.327	0.715	0.449	0.762
⭐ Best Model: XGBoost

Reasons:

Highest F1-score
Highest Recall (critical for churn detection)
Near-perfect AUC = 0.999
Very low false negatives

**Model Interpretability**

Top predictive features:

Tenure

Complain

Order Category (Laptop & Accessory)

Number of Addresses

Marital Status

**Deployment Artifacts**

Saved for production use:

xgboost_churn_model.pkl

scaler.pkl

Can be loaded using Python to make churn predictions on new customers.

**How to Run This Project**
1. Install dependencies
conda env create -f environment.yml
conda activate churn-env

2. Open the notebook
jupyter notebook Project1.ipynb

**Technologies Used**

Python
Scikit-Learn
XGBoost
Pandas / NumPy
Matplotlib / Seaborn
VisualCodeStudio
Git & GitHub

**Author**

Leonardo Rodrigues Quintal
