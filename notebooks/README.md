# 📓 Notebook Overview

This folder contains the main analysis notebook for the **Sepsis Survival Prediction Project**. It combines data preprocessing, modeling, and evaluation into one end-to-end pipeline.

---

## 🧠 Notebook: `sepsis_survival.ipynb`

This notebook walks through the complete process of predicting survival outcomes for sepsis patients using real-world hospital data from Norway.

### 🔍 Key Sections

- **Data Cleaning & Preparation**
  - Removes missing values (e.g. incomplete ICD-10 codes)
  - Engineers features such as number of medical conditions and episode counts
  - Prepares the dataset for modeling

- **Exploratory Data Analysis (EDA)**
  - Visualizes distributions of age, length of stay, and survival outcomes
  - Identifies early trends and possible risk factors

- **Modeling**
  - Trains classification models: logistic regression, decision trees, random forests, bagging, and neural networks
  - Addresses class imbalance using balanced class weights
  - Tunes hyperparameters to maximize **recall** (critical for medical applications)

- **Model Evaluation**
  - Compares model performance using metrics: accuracy, precision, recall, F1-score
  - Selects a **tuned Bagging Classifier** as the top-performing model
  - Highlights feature importance (age, length of stay)

- **Clinical & Ethical Discussion**
  - Discusses model deployment in healthcare contexts
  - Proposes SHAP for future interpretability
  - Frames recommendations under DHH data privacy and transparency guidelines

---

## How to run

### Clone the repository:

```bash
git clone https://github.com/ssithimo/sepsis-survival-ml.git
cd sepsis-survival-ml
```

### Install dependencies:

```bash
pip install -r requirements.txt
```

### Run the notebook:
```bash
jupyter notebook notebooks/sepsis_survival.ipynb
```
