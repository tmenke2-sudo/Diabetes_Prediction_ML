# Diabetes Prediction Using Machine Learning

This project uses machine learning techniques to predict diabetes status using health, lifestyle, and demographic indicators from the **CDC Behavioral Risk Factor Surveillance System (BRFSS)**. The dataset was obtained through Kaggle and contains more than **250,000 survey responses** with variables related to general health, BMI, age, blood pressure, cholesterol, physical activity, and other health indicators.

The goal of the project was to compare multiple predictive modeling approaches and determine which health indicators were most useful in distinguishing individuals with and without diabetes.

## Dataset

The original dataset contains **253,680 observations and 22 variables**.

The target variable, `Diabetes_012`, originally contained three categories:

- `0` = No Diabetes
- `1` = Prediabetes
- `2` = Diabetes

For this project, individuals classified as prediabetic were removed so the problem could be treated as a **binary classification problem** between individuals with and without diabetes.

## Project Workflow

The analysis was completed in **Google Colab using Python**.

The general workflow included:

- Data cleaning and preparation
- Exploratory analysis of health indicators
- Train/test splitting using stratified sampling
- Logistic Regression modeling
- Baseline XGBoost modeling
- XGBoost hyperparameter tuning
- Weighted XGBoost to address class imbalance
- Model comparison using multiple evaluation metrics
- Feature importance analysis
- Permutation importance
- SHAP analysis for model interpretability

## Models

### Logistic Regression

Logistic Regression was used as a baseline model because it provides a straightforward and interpretable approach for understanding how different health indicators relate to diabetes status.

### XGBoost

XGBoost was used to capture more complex and nonlinear relationships within the data.

Several XGBoost models were created, including:

- Baseline XGBoost
- Tuned XGBoost
- Weighted XGBoost

Hyperparameters including tree depth, minimum child weight, gamma, subsampling, column sampling, and learning rate were evaluated during the tuning process.

Because the dataset contained significantly more individuals without diabetes than with diabetes, a weighted XGBoost model was also used to place greater importance on correctly identifying diabetic observations.

## Model Evaluation

Model performance was evaluated using:

- Accuracy
- Sensitivity / Recall
- Specificity
- Precision
- Confusion Matrices
- ROC Curves
- Area Under the Curve (AUC)

The XGBoost models improved the ability to identify individuals with diabetes compared with the initial baseline model. Weighting the model was especially useful for reducing false negatives and improving sensitivity.

## Model Interpretation

In addition to measuring predictive performance, the project explored which variables contributed most strongly to the model's predictions.

Interpretability techniques included:

- XGBoost Feature Importance
- Permutation Importance
- SHAP Values

Some of the strongest predictors identified by the models included:

- General Health
- High Blood Pressure
- BMI
- Age
- High Cholesterol

These results suggest that several commonly measured health indicators can provide useful information when estimating diabetes risk.

## Technologies Used

- Python
- Google Colab
- Pandas
- NumPy
- Scikit-learn
- XGBoost
- Matplotlib
- SHAP

## Purpose

This project was completed as part of graduate-level coursework in the **Master of Science in Business Analytics program at the University of Notre Dame**.

The purpose of the analysis is to demonstrate how machine learning techniques can be applied to a real-world healthcare dataset and how model interpretation tools can help explain the factors influencing predictions.

The models developed in this project are intended for educational and analytical purposes only and should not be considered a medical diagnostic tool.
