# Sepsis Survival Prediction Project 🏥🩺

## Project Overview

Sepsis is a critical medical condition caused by the body's extreme response to infection, leading to life-threatening organ dysfunction. It accounts for significant mortality worldwide and requires rapid diagnosis and intervention to improve patient outcomes.

This project analyzes a large clinical dataset from Norwegian hospitals (110,000+ patient records collected between 2011-2012) to build predictive models that estimate patient survival after sepsis-related hospitalization. Timely and accurate survival prediction can help healthcare providers optimize resource allocation, prioritize intensive care for high-risk patients, and potentially save lives.

---

## 🔧 Technologies Used

- Python  
- scikit-learn  
- Pandas & NumPy  
- Matplotlib & Seaborn  
- SHAP (Explainable AI)

---

## 📊 Dataset

- **Source**: De-identified hospital data from Norwegian patients (2011–2012)  
- **Records**: 110,204 unique patient episodes  
- **Target Variable**: Hospital outcome (0 = survived, 1 = deceased)  
- **Key Features**:
  - Age  
  - Sex  
  - Length of stay  
  - Number of sepsis episodes  
  - Number of ICD-10 diagnoses  

After cleaning, 18 rows with missing ICD codes were removed.

---

## 🧠 Models Used

We tested and compared the following classifiers:

- Logistic Regression  
- Decision Tree  
- Random Forest  
- Bagging Classifier (with decision trees)  
- Feedforward Neural Network

---

## ⚙️ Performance Summary

| Model                 | Accuracy | Recall | F1 Score |
|----------------------|----------|--------|----------|
| Logistic Regression  | 0.78     | 0.63   | 0.65     |
| Decision Tree        | 0.76     | 0.68   | 0.66     |
| **Bagging Classifier** | **0.80** | **0.72** | **0.70** |
| Neural Network        | 0.77     | 0.60   | 0.61     |

- **Best model**: **Bagging Classifier** tuned to prioritize recall  
- **Key predictors**: Age and Length of Stay were the most important features  
- **Interpretability**: Tree-based models provided feature importance; future work includes SHAP integration for transparency

---

## 🔬 Key Findings

- Patients aged **65+** had significantly higher mortality risk  
- **Longer hospital stays** were associated with non-survival, likely due to complications  
- The best-performing model achieved **72% recall**, minimizing false negatives — a critical goal in sepsis management

---

## ⚖️ Ethical & Clinical Considerations

- Optimizing **recall** helps avoid underestimating patient risk  
- Transparency is vital: interpretable models can build trust in clinical settings  
- Dataset was fully anonymized and complies with ethical handling of healthcare data

---

## 📬 Contact

Feel free to reach out if you have questions or suggestions!
