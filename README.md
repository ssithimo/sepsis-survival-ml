# Sepsis Survival Prediction Project 🏥🩺

This repository contains a healthcare analytics project focused on predicting patient survival outcomes for sepsis cases using clinical data from Norway. The goal is to support early detection and improve treatment strategies by leveraging machine learning models and thorough data analysis.

---

## 📁 Repository Structure

### 🗃️ Data  
- **sepsis_dataset.xlsx**

### 📊 Notebook 
- **sepsis_survival.ipynb**
    - Data preprocessing, handling missing values, exploratory data analysis, and visualization of key patient metrics.  
    - Training and tuning multiple classification models including logistic regression, decision trees, bagging classifiers, and neural networks.  
    - Model performance comparison, feature importance analysis, and ethical considerations including explainability with SHAP.
---

## 🚀 Project Overview

Sepsis is a critical medical condition caused by the body's extreme response to infection, leading to life-threatening organ dysfunction. It accounts for significant mortality worldwide and requires rapid diagnosis and intervention to improve patient outcomes.

This project analyzes a large clinical dataset from Norwegian hospitals (110,000+ patient records collected between 2011-2012) to build predictive models that estimate patient survival after sepsis-related hospitalization. Timely and accurate survival prediction can help healthcare providers optimize resource allocation, prioritize intensive care for high-risk patients, and potentially save lives.

Key aspects of the project include:

- **Data Understanding & Cleaning:** Handling missing values, simplifying ICD-10 codes, and engineering meaningful features such as the number of medical conditions and episode frequency.  
- **Exploratory Data Analysis (EDA):** Investigating demographics, length of hospital stay, survival rates, and relationships between variables to inform modeling.  
- **Model Development:** Building and comparing multiple classification models including logistic regression, decision trees, random forests, bagging classifiers, and neural networks. Special emphasis was placed on addressing class imbalance and optimizing recall to reduce false negatives.  
- **Model Evaluation & Interpretation:** Selecting the best performing model (a tuned Bagging Estimator), analyzing feature importance, and exploring explainability techniques such as SHAP to ensure transparency and trustworthiness in clinical applications.  
- **Ethical and Practical Considerations:** Discussing the implications of model deployment in healthcare settings, including patient privacy, data security, and the importance of transparency under the Department of Health and Human Services (DHH) guidelines.

This comprehensive approach not only achieves robust predictive performance but also provides actionable insights and ethical frameworks essential for integrating AI solutions into real-world healthcare environments.

---

## 🔧 Technologies Used

- Python  
- scikit-learn  
- Pandas & NumPy  
- Matplotlib & Seaborn  
- SHAP (Explainable AI)  

---

## ⚖️ Ethical Considerations

This project discusses the importance of transparency, patient data privacy, and ethical deployment of AI in healthcare, referencing the Department of Health and Human Services (DHH) privacy framework.

---

## 📬 Contact

Feel free to reach out if you have questions or suggestions!
