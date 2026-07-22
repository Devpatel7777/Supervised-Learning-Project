# 🏠 House Price Prediction using Machine Learning

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.11-blue?style=for-the-badge&logo=python">
  <img src="https://img.shields.io/badge/Scikit--Learn-ML-orange?style=for-the-badge&logo=scikitlearn">
  <img src="https://img.shields.io/badge/XGBoost-Regression-green?style=for-the-badge">
  <img src="https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter">
</p>

<p align="center">
  An End-to-End Machine Learning Project for Predicting House Prices using the Ames Housing Dataset.
</p>

---

# 🎥 Project Demonstration

## 📺 Watch Full Project Video

👉 **YouTube Demo:**  
**https://youtu.be/YOUR_VIDEO_LINK**

*(Replace the above link with your uploaded YouTube video.)*

---

# 📌 Project Overview

This project focuses on predicting residential house prices using the **Ames Housing Dataset**. It demonstrates a complete end-to-end Machine Learning workflow, including data preprocessing, exploratory data analysis (EDA), feature engineering, model building, evaluation, cross-validation, and hyperparameter tuning.

The objective is to compare multiple regression algorithms and identify the model that provides the most accurate house price predictions.

---

# 📂 Dataset Information

| Feature | Details |
|----------|---------|
| Dataset | Ames Housing Dataset |
| File | train.csv |
| Total Rows | 1460 |
| Total Columns | 81 |
| Target Variable | SalePrice |

---

# 🚀 Project Workflow

```
Load Dataset
      │
      ▼
Exploratory Data Analysis
      │
      ▼
Missing Value Handling
      │
      ▼
Outlier Detection & Removal
      │
      ▼
Feature Engineering
      │
      ▼
Data Preprocessing
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
Best Model Selection
```

---

# 🛠️ Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- XGBoost
- Jupyter Notebook

---

# 🤖 Machine Learning Models

- Linear Regression
- Ridge Regression
- Lasso Regression
- Random Forest Regressor
- XGBoost Regressor

---

# 📊 Model Performance

| Model | RMSE | MAE | R² Score |
|--------|------:|------:|------:|
| Linear Regression | 22,234.16 | 15,647.40 | 0.9105 |
| Ridge Regression | 20,120.48 | 14,546.17 | 0.9267 |
| Lasso Regression | 19,528.72 | 14,240.41 | 0.9310 |
| Random Forest | 23,385.50 | 16,306.49 | 0.9010 |
| **XGBoost** | **19,185.53** | **13,638.48** | **0.9334** |

---

# 🏆 Best Model

**XGBoost Regressor**

### Performance

- RMSE : **19,185.53**
- MAE : **13,638.48**
- R² Score : **0.9334**

XGBoost achieved the best overall performance with the lowest prediction error and the highest coefficient of determination.

---

# 🔍 Cross Validation

- Method: **5-Fold Cross Validation**
- Average RMSE: **0.1208**

---

# ⚙️ Hyperparameter Tuning

RandomizedSearchCV was used to optimize the XGBoost model.

### Best Parameters

```
n_estimators = 300
learning_rate = 0.05
max_depth = 2
subsample = 0.8
colsample_bytree = 0.7
```

Best Cross Validation RMSE

```
0.12137
```

---

# 📁 Project Structure

```
House-Price-Prediction/
│
├── train.csv
├── House_Price_Prediction.ipynb
├── requirements.txt
├── README.md
└── images/
```

---

# ▶️ Getting Started

### Clone Repository

```bash
git clone https://github.com/your-username/House-Price-Prediction.git
```

### Move into Project Folder

```bash
cd House-Price-Prediction
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

### Launch Jupyter Notebook

```bash
jupyter notebook
```

---

# 📈 Results

- Successfully cleaned and preprocessed the dataset.
- Performed Exploratory Data Analysis (EDA).
- Applied Feature Engineering techniques.
- Compared five regression algorithms.
- Used Cross Validation for reliable evaluation.
- Optimized the XGBoost model using RandomizedSearchCV.
- Selected XGBoost as the final model based on RMSE, MAE, and R² Score.

---

# 📧 Contact

**Dev Patel**

📧 Email: devpatel846211@gmail.com

💼 LinkedIn: https://linkedin.com/in/YOUR-LINKEDIN

🐙 GitHub: https://github.com/YOUR-GITHUB-USERNAME

---

# ⭐ Support

If you found this project useful, please consider giving it a ⭐ on GitHub.

---

# 📄 License

This project is intended for educational and learning purposes.
