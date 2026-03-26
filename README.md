# 🌧️ Rainfall Prediction Using Machine Learning  
*A complete end‑to‑end ML pipeline with different types of ML algorithms and ML model comparison*
---
## 📌 Project Overview
This project builds a full machine‑learning workflow to **predict whether it will rain tomorrow** using a real‑world weather dataset.  
It includes:
- Data preprocessing  
- Feature scaling  
- Model training  
- Hyperparameter tuning  
- Model comparison  
- Feature importance analysis  
Multiple ML algorithms were implemented and evaluated to identify the best-performing model.
---
## 🧠 Problem Statement
Given daily weather observations (humidity, pressure, temperature, cloud cover, etc.), the goal is to predict:
```
RainTomorrow = Yes or No
```
This is a **binary classification** problem.
---
## 📂 Project Structure
```
├── data/
│   ├── processed/                !
│   │   └── sydney_rain prediction.csv   
│   └── raw/         
│       └── sydney_rain prediction.xlsx
├── notebooks/
│   ├── rainfall_prediction.ipynb
├── src/
├── .gitignore
├── README.md
└── requirements.txt
```
---
## 🛠️ Technologies Used
- **Python**
- **NumPy, Pandas**
- **Matplotlib, Seaborn**
- **Scikit‑learn**
- **XGBoost**
- **Statsmodels**
---
## 📊 Workflow Summary

### 1️⃣ Data Preprocessing
- Handling missing values  
- Encoding categorical variables  
- Train–test split  
- Feature scaling (StandardScaler for KNN & boosting models)
### 2️⃣ Models Implemented
| Model | Description |
|-------|-------------|
| Logistic Regression | Baseline linear classifier |
| Statsmodels Logit | Statistical interpretation (p‑values, significance) |
| LDA | Linear Discriminant Analysis |
| KNN | Distance‑based classifier with scaling |
| Decision Tree | Basic tree model |
| Bagging | Ensemble of decision trees |
| Random Forest | Strong ensemble baseline |
| Gradient Boosting | Sequential boosting model |
| AdaBoost | Boosting with stumps & RF |
| XGBoost | Final optimized model |
---
## 🧪 Model Training & Evaluation
### ✔️ Logistic Regression
- Baseline model  
- Evaluated using accuracy, confusion matrix, classification report  
- Explored threshold tuning (0.2, 0.3, etc.)
---
### ✔️ LDA (Linear Discriminant Analysis)
- Often outperforms logistic regression  
- Good for linearly separable data  
---
### ✔️ KNN
- Scaled using StandardScaler  
- Tried k = 1, 2, …, 30  
- GridSearchCV used to find optimal k  
---
### ✔️ Decision Tree
- Basic tree with `max_depth=4`  
- Tuned version with `min_samples_leaf=25`, `max_depth=5`
---
### ✔️ Bagging Classifier
- 1000 bootstrapped trees  
- Reduced variance significantly  
---
### ✔️ Random Forest
- 1010 trees  
- Strong performance  
- Hyperparameter tuning using GridSearchCV  
- Tuned parameters included:  
  - `max_features`  
  - `min_samples_split`
---
### ✔️ Gradient Boosting
- Baseline model  
- Tuned version with:  
  - `learning_rate=0.02`  
  - `n_estimators=500`  
  - `max_depth=2`
---
### ✔️ AdaBoost
- Version 1: Decision stumps  
- Version 2: Boosting a Random Forest (stronger)
---
### ⭐ XGBoost (Best Model)
- Baseline:  
  - `max_depth=5`, `n_estimators=5000`, `learning_rate=0.3`
- Hyperparameter tuning using GridSearchCV:  
  - `max_depth`  
  - `gamma`  
  - `subsample`  
  - `colsample_bytree`  
  - `reg_alpha`
- Final tuned model achieved the **highest accuracy**.
---
## 🏆 Final Results
After evaluating all models, **XGBoost** delivered the best performance on the test set.
Typical metrics:
- **Accuracy:** ~0.88–0.92  
- **High recall for rainy days**  
- **Strong generalization**  
- **Clear feature importance insights**
---
## 📈 Feature Importance (XGBoost)
Top predictors typically include:
- **Humidity3pm**  
- **Pressure3pm**  
- **RainToday**  
- **Cloud3pm**  
- **Sunshine**  
These align with real meteorological patterns.
---
## 🚀 How to Run the Project
### 1. Clone the repository
```bash
git clone https://github.com/yourusername/rainfall-prediction.git
cd rainfall-prediction
```
### 2. Install dependencies
```bash
pip install -r requirements.txt
```
### 3. Run the script or notebook
```bash
python main.py
```
or open the Jupyter notebook.
---
## 📌 Future Improvements
- Add SHAP explainability for XGBoost  
- Deploy model using FastAPI  
- Build a Streamlit dashboard  
- Add cross‑validation visualizations  
- Try LightGBM & CatBoost  
---
