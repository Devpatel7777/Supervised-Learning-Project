# Predictive Insight Engine: House Price Prediction Using Supervised Learning

## Project Overview

This project demonstrates the implementation of various **Supervised Learning Regression Algorithms** to predict house prices using real estate data. The objective is to analyze property features, build predictive models, evaluate their performance, and compare different regression techniques.

The project covers the complete machine learning workflow, including data understanding, visualization, model building, evaluation, and performance comparison.

---

## Objectives

* Understand the fundamentals of Supervised Learning.
* Explore relationships between property features and house prices.
* Implement Simple Linear Regression.
* Implement Multiple Linear Regression.
* Implement Polynomial Regression.
* Evaluate models using regression metrics.
* Analyze overfitting and underfitting.
* Understand Gradient Descent optimization.

---

## Dataset Information

The dataset contains **4,200 real estate property records** with various features affecting house prices.

### Features

| Feature              | Description                   |
| -------------------- | ----------------------------- |
| house_id             | Unique property identifier    |
| area_sqft            | Property area in square feet  |
| bedrooms             | Number of bedrooms            |
| bathrooms            | Number of bathrooms           |
| location_score       | Location quality score        |
| age_years            | Property age                  |
| distance_city_km     | Distance from city center     |
| lot_size_sqft        | Plot size                     |
| has_garage           | Garage availability           |
| has_pool             | Swimming pool availability    |
| renovation_years_ago | Years since last renovation   |
| house_price_inr      | Target variable (House Price) |

---

## Technologies Used

* Python
* Jupyter Notebook
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-Learn

---

## Project Workflow

### Part A: Conceptual Understanding

* Supervised Learning
* Regression vs Classification
* Simple Linear Regression
* Assumptions of Linear Regression
* Bias-Variance Tradeoff
* Overfitting vs Underfitting

### Part B: Data Understanding & Preparation

* Dataset loading
* Data exploration
* Missing value analysis
* Feature selection
* Correlation analysis
* Data visualization
* Train-test splitting

### Part C: Simple Linear Regression

* Model training using House Area
* Regression line visualization
* Slope and intercept interpretation

### Part D: Model Evaluation

Performance measured using:

* Mean Squared Error (MSE)
* Mean Absolute Error (MAE)
* Root Mean Squared Error (RMSE)
* R² Score
* Adjusted R² Score

### Part E: Multiple Linear Regression

* Training using all features
* Performance comparison with Simple Linear Regression

### Part F: Polynomial Regression

* Degree-2 Polynomial Features
* Non-linear relationship modeling
* Overfitting analysis

### Part G: Gradient Descent

* Batch Gradient Descent
* Stochastic Gradient Descent (SGD)
* Mini-Batch Gradient Descent

### Part H: Bias-Variance Analysis

* Underfitting Analysis
* Overfitting Analysis
* Model Generalization Comparison

---

## Data Visualization

The project includes:

* Correlation Heatmap
* Area vs House Price Scatter Plot
* Location Score vs House Price Scatter Plot
* Pair Plot Analysis
* Residual Plot
* Regression Line Visualization

---

## Machine Learning Models

### 1. Simple Linear Regression

Predicts house prices using only property area.

### 2. Multiple Linear Regression

Uses all available property features for prediction.

### 3. Polynomial Regression

Captures non-linear relationships between features and target variable.

---

## Evaluation Metrics

| Metric      | Purpose                           |
| ----------- | --------------------------------- |
| MSE         | Average squared prediction error  |
| MAE         | Average absolute prediction error |
| RMSE        | Error in original units           |
| R² Score    | Goodness of fit                   |
| Adjusted R² | Penalizes unnecessary features    |

---

## Key Findings

* The dataset was clean and required minimal preprocessing.
* Property area and location score showed strong positive relationships with house prices.
* Multiple Linear Regression achieved better performance than Simple Linear Regression.
* Polynomial Regression captured non-linear patterns but may increase model complexity.
* Multiple Linear Regression provided the best balance between prediction accuracy and generalization.


## Learning Outcomes

Through this project, the following concepts were applied:

* Data Exploration
* Data Visualization
* Feature Selection
* Regression Modeling
* Model Evaluation
* Gradient Descent
* Bias-Variance Tradeoff
* Overfitting & Underfitting Analysis

---

## Author

**Dev Patel**
