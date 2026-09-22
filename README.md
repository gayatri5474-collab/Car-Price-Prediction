# Car Price Prediction

Machine learning project for predicting car prices using regression, feature engineering, regularisation and model evaluation.

## Project Overview

This project analyses a car price dataset containing numerical and categorical features to understand the factors associated with car prices and build regression models for price prediction.

The project focuses on comparing:

- Linear Regression
- Ridge Regression
- Lasso Regression

Regularisation techniques are used to control coefficient magnitude, address multicollinearity and evaluate model generalisation.

## Objectives

- Explore the car price dataset and understand feature distributions
- Identify and handle missing values and outliers
- Analyse relationships between numerical and categorical features and car price
- Perform feature engineering and categorical encoding
- Transform the target variable to improve model behaviour
- Build a baseline Linear Regression model
- Apply Ridge and Lasso regularisation
- Tune regularisation parameters using cross-validation
- Compare model performance and coefficients
- Analyse the effect of regularisation on model stability and feature selection

## Dataset

The dataset contains **15,915 records** and includes numerical and categorical variables related to cars.
The dataset is available on Kaggle:

[Car Price Data for Car Price Prediction Project](https://www.kaggle.com/datasets/gayatribehera5474/car-price-data-for-car-price-prediction-project)

Key features include:

- Car make and model
- Age
- Mileage (`km`)
- Horsepower (`hp_kW`)
- Engine displacement
- Weight
- Gears
- Fuel type
- Body type
- Drive chain
- Gearing type
- Previous owners
- Inspection status
- Comfort and convenience features
- Entertainment and media features
- Safety and security features

The target variable is **car price**.

## Data Preparation

The following data preparation steps were performed:

- Checked for missing values
- Analysed numerical and categorical distributions
- Identified low-frequency categories and class imbalance
- Grouped rare categorical values where appropriate
- Identified potential outliers
- Capped extreme values at the 1st and 99th percentiles
- Applied log transformation to the price variable

The dataset contained no missing values, so no imputation was required.

## Exploratory Data Analysis

Key observations from the analysis include:

- `km` and `age` show right-skewed distributions.
- Price is negatively associated with mileage and age.
- `hp_kW` has a strong positive relationship with price.
- `hp_kW` and `Displacement_cc` show a strong positive correlation.
- Different car makes, body types, fuel types and gearing types show differences in average price.
- The original price distribution is right-skewed, while the log-transformed target is substantially more symmetric.

## Feature Engineering

Feature engineering included:

- Creation of `log_price` using a log transformation
- Cleaning and consolidation of categorical variables
- One-hot encoding of categorical features
- Scaling of numerical features
- Analysis of multi-value categorical features such as:
  - Comfort & Convenience
  - Entertainment & Media
  - Extras
  - Safety & Security
- Variance Inflation Factor (VIF) analysis to identify multicollinearity

The data was split into:

- **80% Training**
- **20% Testing**

with `random_state = 42`.

## Machine Learning Models

### 1. Linear Regression

A baseline Linear Regression model was developed and evaluated using:

- RMSE
- MAE
- R² Score

Residual analysis, Q-Q plots and VIF analysis were also performed to assess model behaviour and assumptions.

### 2. Ridge Regression

Ridge Regression was applied to reduce the magnitude of regression coefficients and improve model stability.

The regularisation parameter (`alpha`) was tuned using cross-validation.

The final tuned Ridge model used an alpha value of approximately **50.66**.

### 3. Lasso Regression

Lasso Regression was used to investigate both regularisation and feature selection.

The model can shrink some coefficients to exactly zero, effectively eliminating less influential features.

The tuned Lasso model was compared with Linear and Ridge Regression based on test performance and coefficient behaviour.

## Model Comparison

The three models were compared using RMSE, MAE and R².

| Model | RMSE | MAE | R² |
| --- | ---: | ---: | ---: |
| Linear Regression | 0.109663 | 0.082777 | 0.924763 |
| Ridge Regression | 0.109656 | 0.082746 | 0.924772 |
| Lasso Regression | 0.109672 | ~0.0828 | 0.924751 |

The models produced very similar predictive performance.

Ridge showed a small improvement in test performance while also reducing coefficient magnitude. Lasso provided additional interpretability through feature elimination.

## Key Insights

- Horsepower (`hp_kW`) is an important predictor of car price.
- Mileage and vehicle age are negatively associated with price.
- Multicollinearity was observed between some numerical predictors, particularly horsepower and engine displacement.
- Ridge Regression helped control coefficient magnitude and improve model stability.
- Lasso Regression eliminated some less influential features by reducing their coefficients to zero.
- Regularisation improved stability and generalisation without producing a major change in predictive accuracy.
- The baseline Linear Regression model already performed well because the dataset contained strong predictive features.

## Conclusion

The analysis demonstrates how regularisation can be used to improve the stability and interpretability of linear regression models.

Linear, Ridge and Lasso Regression achieved similar predictive performance on the transformed price target. Ridge provided a balance between coefficient shrinkage and predictive performance, while Lasso demonstrated the usefulness of regularisation for feature selection.

Overall, the project shows the complete workflow from exploratory data analysis and feature engineering to regression modelling, hyperparameter tuning and model comparison.

## Project Files

- `Regularisation_Car_Price_Prediction-Gayatri Behera.ipynb` — Complete analysis and modelling notebook
- `Report_Regularisation_Car_Price_Prediction-Gayatri_Behera.pdf` — Detailed project report

## Tools & Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Exploratory Data Analysis
- Feature Engineering
- Linear Regression
- Ridge Regression
- Lasso Regression
- Cross-validation
- Statistical Analysis

## Author

**Gayatri Behera**

Data Analytics | Python | SQL | Power BI | Machine Learning | Engineering Analytics
