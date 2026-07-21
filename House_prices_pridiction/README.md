# House Price Prediction — Supervised Learning

## Project Overview

This project presents an end-to-end Supervised Machine Learning solution for predicting residential house sale prices using the Ames Housing Dataset.

The project represents a real-world PropTech use case where machine learning can be used to estimate property values based on different characteristics such as overall quality, living area, basement area, garage area, construction year, neighborhood, and other housing attributes.

The main objective is to build, evaluate, and compare multiple regression models and identify the model that provides the most accurate house price predictions.

---

## Problem Statement

House prices depend on several factors including property size, quality, location, age, available facilities, and construction characteristics.

The objective of this project is to develop a regression model that can predict the `SalePrice` of a house using the available property features.

Since `SalePrice` is a continuous numerical variable, this is a **Supervised Learning Regression Problem**.

---

## Dataset

The project uses the **Ames Housing Dataset** from the House Prices: Advanced Regression Techniques dataset.

### Dataset Details

| Attribute | Description |
|---|---|
| Dataset | Ames Housing Dataset |
| Training Records | 1,460 |
| Input Features | 79 |
| Data Types | Numerical and Categorical |
| Target Variable | SalePrice |
| Machine Learning Task | Regression |

Only the training dataset was used and an independent train-test split was performed for model evaluation.

---

## Project Workflow

The project follows the following machine learning workflow:

1. Problem Framing and Regression Theory
2. Dataset Loading and Understanding
3. Exploratory Data Analysis
4. Target Variable Analysis
5. Missing Value Analysis
6. Outlier Detection and Removal
7. Feature Engineering
8. Categorical Encoding
9. Numerical Feature Transformation
10. Feature Scaling
11. Train-Test Split
12. Linear Regression
13. Ridge Regression
14. Lasso Regression
15. Random Forest Regressor
16. XGBoost Regressor
17. Cross-Validation
18. Hyperparameter Tuning
19. Model Evaluation and Comparison

---

# Exploratory Data Analysis

Exploratory Data Analysis was performed to understand the structure and characteristics of the dataset.

The analysis includes:

- Dataset shape
- Dataset information
- Descriptive statistics
- Numerical and categorical feature identification
- Missing value analysis
- SalePrice distribution analysis
- Q-Q plot
- Numerical feature distributions
- Feature skewness analysis
- Categorical count plots
- Correlation analysis
- Scatter plots
- Box plots
- Outlier detection

---

## Target Variable Analysis

The target variable of this project is:

```text
SalePrice
```

The original `SalePrice` distribution was positively skewed.

A `log1p()` transformation was applied to reduce the skewness and obtain a more normally distributed target variable.

During model evaluation, `expm1()` was used to convert the predictions back to the original house-price scale before calculating RMSE and MAE.

---

# Missing Value Handling

The Ames Housing Dataset contains several features with missing values.

Missing values were handled based on the meaning and data type of each feature.

For categorical variables where a missing value indicates that a facility does not exist, the missing values were represented using:

```text
None
```

For appropriate numerical features where a missing value indicates the absence of a facility, the values were replaced with:

```text
0
```

Remaining numerical missing values were handled using median imputation.

Columns with very high missing percentages were also analyzed for removal.

---

# Outlier Detection and Removal

The relationship between `GrLivArea` and `SalePrice` was analyzed to identify unusual observations.

Two extreme observations were identified using the condition:

```text
GrLivArea > 4000
SalePrice < 300000
```

These two observations were removed before model training.

Outliers of this type can negatively affect regression models because they do not follow the general relationship between living area and house price.

After outlier removal, the dataset contained:

```text
1458 observations
```

---

# Feature Engineering

Five additional features were created from the existing housing attributes.

## TotalSF

```text
TotalSF = TotalBsmtSF + 1stFlrSF + 2ndFlrSF
```

This feature represents the total usable area of the house.

## HouseAge

```text
HouseAge = YrSold - YearBuilt
```

This represents the age of the property when it was sold.

## RemodAge

```text
RemodAge = YrSold - YearRemodAdd
```

This represents the number of years since the property was remodeled.

## HasGarage

```text
1 = Garage Available
0 = No Garage
```

## HasPool

```text
1 = Pool Available
0 = No Pool
```

These engineered features provide additional information that can help machine learning models better understand property characteristics.

---

# Encoding and Feature Transformation

The dataset contains both numerical and categorical variables.

Different encoding methods were applied based on the type of categorical feature.

### Ordinal Encoding

Quality-related variables were converted into numerical values while preserving their natural ranking.

Example:

```text
None = 0
Po   = 1
Fa   = 2
TA   = 3
Gd   = 4
Ex   = 5
```

### One-Hot Encoding

Nominal categorical variables were converted into numerical representations using One-Hot Encoding.

### High-Cardinality Features

High-cardinality categorical variables such as `Neighborhood` were converted into numerical form for model training.

---

# Skewness Transformation

Highly skewed numerical features were identified and transformed using:

```python
np.log1p()
```

The purpose of this transformation was to reduce extreme skewness and improve the distribution of numerical variables.

---

# Feature Scaling

Continuous numerical features were standardized using:

```text
StandardScaler
```

Standardization helps place numerical variables on comparable scales, which is particularly useful for regression models such as Ridge and Lasso.

---

# Train-Test Split

The processed dataset was divided into training and testing sets using an:

```text
80% Training
20% Testing
```

split.

The random state used was:

```python
random_state=42
```

The training data was used for model development while the test data was kept separate for final model evaluation.

---

# Regression Models

Five different regression algorithms were trained and evaluated.

## 1. Linear Regression

Linear Regression was used as the baseline model.

### Performance

```text
RMSE     : $24,487.41
MAE      : $16,540.35
R² Score : 0.8914
```

---

## 2. Ridge Regression

Ridge Regression applies L2 regularization to control coefficient magnitude and reduce overfitting.

`RidgeCV` was used to automatically select the best alpha value.

### Best Alpha

```text
100.0
```

### Performance

```text
RMSE     : $22,732.77
MAE      : $15,840.09
R² Score : 0.9064
```

---

## 3. Lasso Regression

Lasso Regression applies L1 regularization.

L1 regularization can reduce some feature coefficients toward zero and therefore can also provide feature-selection behavior.

### Best Alpha

```text
0.01
```

### Performance

```text
RMSE     : $20,937.42
MAE      : $15,372.18
R² Score : 0.9206
```

Among the three linear regression approaches, Lasso Regression achieved the strongest performance.

---

## 4. Random Forest Regressor

Random Forest is an ensemble learning algorithm that combines multiple decision trees.

The model was trained using:

```text
n_estimators = 200
max_depth = 10
random_state = 42
```

### Performance

```text
RMSE     : $23,427.73
MAE      : $16,418.78
R² Score : 0.9006
```

Feature importance analysis was also performed to identify the most influential predictors.

---

## 5. XGBoost Regressor

XGBoost is a gradient boosting algorithm that builds decision trees sequentially.

Each new tree attempts to reduce the prediction errors produced by previous trees.

The initial XGBoost model was trained using:

```text
n_estimators = 500
learning_rate = 0.05
max_depth = 4
subsample = 0.8
colsample_bytree = 0.8
random_state = 42
```

### Performance

```text
RMSE     : $21,333.05
MAE      : $14,965.10
R² Score : 0.9176
```

---

# Cross-Validation

Five-Fold Cross-Validation was performed on the XGBoost model.

The notebook produced the following RMSE scores on the log-transformed target:

```text
Fold 1 : 0.11
Fold 2 : 0.13
Fold 3 : 0.13
Fold 4 : 0.13
Fold 5 : 0.11

Mean CV RMSE       : 0.12
Standard Deviation : 0.01
```

These cross-validation scores are on the log-transformed target scale and therefore should not be directly compared numerically with RMSE calculated on the original dollar price scale.

The relatively small variation between folds indicates reasonably consistent performance across the cross-validation splits.

---

# Hyperparameter Tuning

`RandomizedSearchCV` was used to optimize the XGBoost model.

The search evaluated 20 random parameter combinations using 3-Fold Cross-Validation.

### Best Parameters

```text
subsample         : 0.7
n_estimators      : 500
max_depth         : 3
learning_rate     : 0.03
colsample_bytree  : 0.7
```

The best Cross-Validation RMSE on the log-transformed target was approximately:

```text
0.12188
```

---

# Tuned XGBoost Performance

After applying the best hyperparameters, the tuned XGBoost model was evaluated on the test dataset.

### Performance

```text
RMSE     : $19,842.53
MAE      : $14,060.27
R² Score : 0.9287
```

The tuned XGBoost model improved the predictive performance compared with the original XGBoost model.

---

# Model Comparison

| Model | RMSE | MAE | R² Score |
|---|---:|---:|---:|
| Linear Regression | $24,487.41 | $16,540.35 | 0.8914 |
| Ridge Regression | $22,732.77 | $15,840.09 | 0.9064 |
| Lasso Regression | $20,937.42 | $15,372.18 | 0.9206 |
| Random Forest | $23,427.73 | $16,418.78 | 0.9006 |
| XGBoost | $21,333.05 | $14,965.10 | 0.9176 |
| **Tuned XGBoost** | **$19,842.53** | **$14,060.27** | **0.9287** |

---

# Best Model

Based on the current notebook results, the **Tuned XGBoost Regressor** achieved the best overall predictive performance.

It produced:

```text
RMSE     : $19,842.53
MAE      : $14,060.27
R² Score : 0.9287
```

The tuned model achieved the lowest RMSE and MAE and the highest R² Score among the tested models.

An R² score of approximately `0.9287` indicates that the model explains approximately **92.87% of the variation in house sale prices in the test dataset**.

XGBoost is suitable for this dataset because it can capture complex nonlinear relationships and interactions between housing characteristics.

---

# Key Findings

The project demonstrates that:

- House prices can be predicted effectively using supervised regression techniques.
- Log transformation improves the distribution of the highly skewed SalePrice target.
- Feature engineering provides additional useful information for prediction.
- Regularized regression models outperform the basic Linear Regression model in this experiment.
- Lasso Regression achieved strong performance among the linear models.
- Tree-based ensemble models can capture complex nonlinear patterns.
- Hyperparameter tuning improved the performance of XGBoost.
- Tuned XGBoost achieved the strongest overall test performance.

---

# Technologies and Libraries

The project uses:

```text
Python
Pandas
NumPy
Matplotlib
Seaborn
SciPy
Scikit-learn
XGBoost
Jupyter Notebook
```

---

# Project Structure

```text
house-price-regression-supervised-learning/
│
├── HousePrice_SupervisedLearning.ipynb
├── train.csv
├── house_price_model.pkl
├── summary_report.md
├── requirements.txt
└── README.md
```

---

# How to Run

1. Clone or download the repository.
2. Install the required Python libraries.
3. Add `train.csv` to the project directory.
4. Open the Jupyter Notebook.
5. Run the notebook cells from top to bottom.
6. Review the EDA, preprocessing, model training, tuning, and comparison results.

Install dependencies using:

```bash
pip install -r requirements.txt
```

---

# Video Demonstration

A 5–10 minute recorded demonstration of the project will be provided.

The demonstration covers:

- Business problem
- Dataset
- Exploratory Data Analysis
- Missing-value handling
- Outlier removal
- Feature engineering
- Encoding and scaling
- Regression models
- Cross-validation
- Hyperparameter tuning
- Model comparison
- Final results

**Video Link:** Add Google Drive or YouTube Unlisted link here.

---

# Future Improvements

Future improvements can include:

- Building the complete preprocessing and model workflow using `ColumnTransformer` and `Pipeline`
- Additional feature engineering
- Advanced hyperparameter optimization
- Ensemble and stacking techniques
- SHAP-based model interpretation
- More recent real-estate transaction data
- Geographic and market-level features
- Deployment using Streamlit or FastAPI
- Model monitoring after deployment

---

# Author

**Dev Patel**



## Disclaimer

This project was developed for educational and practical examination purposes using the Ames Housing Dataset.