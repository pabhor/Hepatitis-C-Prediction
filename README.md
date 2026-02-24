# 🩺 Hepatitis C Prediction – Multi-Class Liver Disease Classification

## 📌 Project Overview

This project focuses on predicting liver disease stages using clinical laboratory data.  
The objective is to classify patients into one of five categories:

- 0 – Blood Donor
- 0s – Suspect Blood Donor
- 1 – Hepatitis
- 2 – Fibrosis
- 3 – Cirrhosis

The model is built using Logistic Regression with hyperparameter tuning via GridSearchCV and evaluated using weighted F1-score and accuracy.

---

## 📊 Dataset Description

The dataset contains demographic and biochemical features including:

- Age
- Sex
- ALB (Albumin)
- ALT (Alanine Aminotransferase)
- AST (Aspartate Aminotransferase)
- ALP (Alkaline Phosphatase)
- BIL (Bilirubin)
- CHE (Cholinesterase)
- GGT
- PROT (Total Protein)

The target variable represents liver disease progression stages.

---

## 🔎 Exploratory Data Analysis (EDA)

### Univariate Analysis
- Examined feature distributions using histograms and boxplots.
- Identified skewness in liver enzyme features (ALT, AST, GGT).
- Detected outliers in enzyme-related variables.

### Target Distribution
- Significant class imbalance observed.
- Approximately 86% of samples belong to the Blood Donor class.
- Minority classes include Hepatitis, Fibrosis, and Cirrhosis.

### Bivariate Analysis
- Compared enzyme levels across disease stages.
- Observed higher ALT and AST levels in Hepatitis patients.
- Lower Albumin levels associated with advanced liver damage.

### Correlation Heatmap
- Strong positive correlation between ALT and AST.
- Moderate correlation between ALP and Bilirubin.
- Negative relationship between Albumin and severe liver damage.
- Heatmap used to understand multicollinearity and feature relationships.

---

## ⚖️ Handling Class Imbalance

Due to dominance of the Blood Donor class, class imbalance was addressed using:

- SMOTE (Synthetic Minority Over-sampling Technique)
- Applied to the training data to improve minority class representation.

---

## 🤖 Model Development

### Pipeline Architecture

- StandardScaler (feature normalization)
- Logistic Regression classifier

### Hyperparameter Tuning

GridSearchCV was used with 5-fold cross-validation to tune:

- Regularization strength (C)
- Multi-class strategy (one-vs-rest vs multinomial)
- L2 regularization penalty

Scoring metric during tuning: Accuracy  
Final evaluation metric: Weighted F1-score

---

## 📈 Model Evaluation

Evaluation was performed on:

- Validation Set
- Test Set

Metrics reported:

- Accuracy
- Weighted F1-score

Weighted F1-score was prioritized to account for class imbalance.

---

## 💾 Model Persistence

The final optimized model pipeline was saved using:

- joblib
- File: liver_disease_logreg_5class.pkl

This allows direct loading for inference or deployment.

---

## 🗂️ Project Structure

Hepatitis-C-Prediction/
- Data_pipeline.ipynb
- liver_disease_logreg_5class.pkl
- README.md
- .gitignore

---

## 🛠️ Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Imbalanced-learn (SMOTE)
- Joblib

---

## 🎯 Business / Clinical Relevance

- Enables early detection of liver disease progression.
- Supports classification across multiple severity stages.
- Provides interpretable coefficients through Logistic Regression.
- Addresses real-world class imbalance challenges.

---

## 🔮 Future Enhancements

- Compare with tree-based models (Random Forest, XGBoost)
- Use macro F1-score for stricter imbalance evaluation
- Add SHAP-based feature importance
- Deploy as REST API or Streamlit web application
- Introduce probability-based risk scoring system

---

## 🚀 How to Run

1. Clone the repository
2. Install dependencies
3. Run Data_pipeline.ipynb
4. Trained model will be saved as liver_disease_logreg_5class.pkl

---

## 📬 Author

Prabhu Bhor  
Machine Learning | Clinical AI | Data Science
