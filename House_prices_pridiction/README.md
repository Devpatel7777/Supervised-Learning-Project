# House Price Prediction using Machine Learning

An end-to-end Machine Learning project for predicting residential house prices using the Ames Housing Dataset. This project demonstrates the complete workflow from data preprocessing to model evaluation and selection.

---

## Project Demonstration

**Project Video:**  
https://drive.google.com/file/d/1FzJ0IsmxKkRDTckrQvj8tH1otz1ajV8-/view?usp=sharing

---

## Project Overview

The objective of this project is to predict house prices using supervised machine learning regression algorithms. The project includes exploratory data analysis, data preprocessing, feature engineering, model training, model evaluation, cross-validation, and hyperparameter tuning.

---

## Dataset

| Attribute | Value |
|----------|--------|
| Dataset | Ames Housing Dataset |
| File | train.csv |
| Records | 1460 |
| Features | 81 |
| Target Variable | SalePrice |

---

## Project Workflow

```
Dataset
   │
   ▼
Data Cleaning
   │
   ▼
Exploratory Data Analysis
   │
   ▼
Feature Engineering
   │
   ▼
Preprocessing
   │
   ▼
Train-Test Split
   │
   ▼
Regression Models
   │
   ▼
Model Evaluation
   │
   ▼
Cross Validation
   │
   ▼
Hyperparameter Tuning
   │
   ▼
Final Model
```

---

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- XGBoost
- Jupyter Notebook

---

## Machine Learning Models

- Linear Regression
- Ridge Regression
- Lasso Regression
- Random Forest Regressor
- XGBoost Regressor

---

## Model Performance

| Model | RMSE | MAE | R² Score |
|------|------:|------:|------:|
| Linear Regression | 22,234.16 | 15,647.40 | 0.9105 |
| Ridge Regression | 20,120.48 | 14,546.17 | 0.9267 |
| Lasso Regression | 19,528.72 | 14,240.41 | 0.9310 |
| Random Forest | 23,385.50 | 16,306.49 | 0.9010 |
| XGBoost | **19,185.53** | **13,638.48** | **0.9334** |

---

## Best Model

After evaluating all regression models, **XGBoost Regressor** achieved the best overall performance.

| Metric | Value |
|--------|-------|
| RMSE | 19,185.53 |
| MAE | 13,638.48 |
| R² Score | 0.9334 |

---

## Cross Validation

**Method**

- 5-Fold Cross Validation

**Average RMSE**

```
0.1208
```

---

## Hyperparameter Tuning

RandomizedSearchCV was used to optimize the XGBoost model.

### Best Parameters

```text
n_estimators = 300
learning_rate = 0.05
max_depth = 2
subsample = 0.8
colsample_bytree = 0.7
```

### Best Cross Validation Score

```text
0.12137
```

---

## Repository Structure

```
House-Price-Prediction/
│
├── train.csv
├── House_Price_Prediction.ipynb
├── requirements.txt
└── README.md
```

---

## Installation

Clone the repository

```bash
git clone https://github.com/your-username/House-Price-Prediction.git
```

Move to the project directory

```bash
cd House-Price-Prediction
```

Install dependencies

```bash
pip install -r requirements.txt
```

Launch Jupyter Notebook

```bash
jupyter notebook
```

---

## Results

- Performed Exploratory Data Analysis (EDA)
- Handled Missing Values
- Removed Outliers
- Applied Feature Engineering
- Trained Five Regression Models
- Performed Cross Validation
- Applied Hyperparameter Tuning
- Selected XGBoost as the Final Model

---

## Author

**Dev Patel**
