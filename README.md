# Fraud Detection in Credit Card Transactions  
_Logistic Regression & XGBoost_

## Overview  
This project focuses on detecting fraudulent credit card transactions using machine learning models. The goal was to build a pipeline that identifies fraud while handling class imbalance effectively.

Rather than relying on accuracy, the models are primarily evaluated using the Matthews Correlation Coefficient (MCC), which provides a more balanced measure of performance across both fraud and non-fraud classes.

---

## Business Context  
A new credit card company operating in the western United States wants to position itself as one of the safest providers in the market. As the data scientist on the team, the objective is to:

- Predict whether a transaction is fraudulent  
- Avoid misleading evaluation metrics due to class imbalance  
- Build a model that performs well across both fraud and non-fraud classes  

---

## Dataset  
The dataset contains credit card transactions with:

- Customer details (age, location, etc.)  
- Transaction details (amount, merchant, category)  
- Geographic data (state-level information)  
- Fraud label (fraud vs. non-fraud)  

---

## Project Goals  
- Build predictive models to classify fraud vs. non-fraud  
- Compare Logistic Regression and XGBoost  
- Evaluate performance using MCC as the primary metric  

---

## Approach  

### 1. Data Exploration  
- Identified categories with higher fraud rates  
- Observed relationships between transaction amount and fraud likelihood  
- Explored geographic distribution of fraud  

### 2. Feature Engineering  
- Encoded categorical variables  
- Scaled numerical features where necessary  
- Prepared dataset for model training  

### 3. Modeling  

#### Logistic Regression  
- Used as a baseline model  
- Interpretable and efficient  
- Applied class weighting to address imbalance  

#### XGBoost  
- Captures nonlinear relationships and feature interactions  
- More effective for complex patterns  
- Tuned for improved performance  

---

## Results  

### Model Comparison (Based on MCC)

| Model                | MCC Performance |
|---------------------|----------------|
| Base Logistic Regression | 0.327626      | 
| Weighted Logistic Regression  | 0.339346        | 
| KBest Logistic Regression | 0.423349      | 
| XGBoost with KBest | 0.819987        | 
| XGBoost (Categorical) | 0.846308      | 
| Base XGBoost  | 0.850372        | 
| XGBoost (Selected features)  | 0.855610        | 
| Tuned XGBoost (Selected features) | 0.861017      | 
| Tuned XGBoost (Full features) | 0.864180  | 


### Key Takeaways  

- XGBoost achieved a higher MCC, indicating better overall performance across both classes  
- Logistic Regression provided a solid baseline but was less effective for complex relationships  
- MCC revealed differences in performance that accuracy alone would not capture  

---

## Key Insights  

- Fraud likelihood varies by transaction category  
- Certain transaction amounts are more associated with fraud  
- Geographic variation exists across states  
- Behavioral patterns are more predictive than demographic features  

---

## Motivation  

This project was designed to simulate a real-world fraud detection system, where:

- Data is imbalanced  
- Accuracy can be misleading  
- Proper evaluation metrics are critical  

Using MCC demonstrates an understanding of how to evaluate models appropriately in real-world scenarios, not just how to build them.
