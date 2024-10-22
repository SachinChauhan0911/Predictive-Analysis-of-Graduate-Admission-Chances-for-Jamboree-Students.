# Project Title:
- Predictive Analysis of Graduate Admission Chances for Jamboree Students

# Problem Statement:
- Jamboree has recently introduced a feature that allows students to estimate their chances of gaining admission into Ivy League schools based on various factors. This project 
aims to analyze the significant factors affecting graduate admissions from an Indian perspective. The analysis will help predict the likelihood of a student's admission, 
given key variables such as CGPA, GRE, TOEFL scores, and others. This will assist Jamboree in providing more accurate admission predictions and recommendations to students.

# Potential Impact:
- Provide actionable insights to Jamboree for better advising students on areas to improve to boost their admission chances.
Enhance the feature on Jamboree’s platform by offering personalized admission predictions, which will improve user engagement.
Help Jamboree students make data-driven decisions, leading to higher satisfaction and more successful admission outcomes.    

# Approach:
- Perform exploratory data analysis (EDA) to understand the relationship between variables such as CGPA, GRE, TOEFL, SOP, LOR, research experience, and university rating with the chances of admission.
- Apply multiple regression models, including Linear Regression, Ridge, and ElasticNet, to predict the chances of admission.
- Evaluate and compare model performance using R² scores and error metrics on unseen data.
- Identify and rank the importance of factors that significantly influence admission chances.
- This project analyzes a dataset provided by Jamboree to predict the likelihood of graduate admission to top universities using various machine learning algorithms. The dataset consists of 500 rows and 9 features. The target is the probability of graduate admission based on independent variables like GRE scores, TOEFL scores, and CGPA.
## Dataset
- Rows: 500
- Features: 9
- Unique Identifier: Serial No (dropped as it does not contribute to model prediction)

## Model Pipeline
### Data Preprocessing:
- Dropped the Serial No column as it is a unique identifier and doesn’t help in prediction.
- Split the dataset into training and testing sets.
### Model Selection:
- Applied Linear Regression (using sklearn), Ordinary Least Squares (OLS), Ridge, Lasso, and Elastic Net models to predict the target.
### Model Performance:
- Evaluated models based on R² Score, Adjusted R² Score, MSE, MAE, and RMSE.

## Model Results
###  1. Linear Regression (Sklearn)
#### Training Set:
- R² Score: 0.82
- Adjusted R² Score: 0.82
- MSE: 0.0
- MAE: 0.04
- RMSE: 0.06
#### Test Set:
- R² Score: 0.82
- Adjusted R² Score: 0.81
- MSE: 0.0
- MAE: 0.04
- RMSE: 0.06

### 2. Linear Regression (OLS)
#### Training Set:
- R² Score: 0.82
#### Test Set:
- R² Score: 0.81

### 3. Ridge Regression
#### Training Set:
- R² Score: 0.82
- Adjusted R² Score: 0.82
- MSE: 0.0
- MAE: 0.04
- RMSE: 0.06
#### Test Set:
- R² Score: 0.82
- Adjusted R² Score: 0.82
- MSE: 0.0
- MAE: 0.04
- RMSE: 0.06

### 4. Lasso Regression
#### Training Set:
- R² Score: 0.0
- Adjusted R² Score: -0.02
- MSE: 0.02
- MAE: 0.11
- RMSE: 0.14
#### Test Set:
- R² Score: -0.01
- Adjusted R² Score: -0.09
- MSE: 0.02
- MAE: 0.12
- RMSE: 0.14

### 5. Elastic Net Regularization
- Hyperparameter tuning was done using GridSearchCV to find the optimal alpha and l1_ratio for Elastic Net regularization.
Final model performance showed improved regularization over Lasso with similar results to Ridge.

### 6. Models Comparison
![text](https://github.com/SachinChauhan0911/Linear-Regression---Jamboree-Education-Case-Study/blob/main/images/Screenshot%202024-10-22%20at%207.29.03%20AM.png)

### 7. Feature Importances for different models
![text2](https://github.com/SachinChauhan0911/Linear-Regression---Jamboree-Education-Case-Study/blob/main/images/Screenshot%202024-10-22%20at%207.35.06%20AM.png)

#### Key Insights
- Linear Regression and Ridge Regression performed the best with consistent R² and Adjusted R² scores of 0.82 on training and test datasets.
- Lasso Regression underperformed with R² scores close to zero, indicating poor model fit.
- The model performs poorly with Lasso Regularization, as it drives the weights of all features to **zero**. This suggests that Lasso may be too aggressive in shrinking feature coefficients to zero, which negatively affects performance.
- Homoscedasticity: Residuals show constant variance, so homoscedasticity is assumed to be met.
- Heteroscedasticity: Evidence of heteroscedasticity in the residuals suggests that the variance of the residuals is not constant - across the levels of independent variables. This may affect the linear regression model's validity.
- Regularization: Ridge regression provided better performance over Lasso and Elastic Net regularization with similar results to the Linear Regression model.




















