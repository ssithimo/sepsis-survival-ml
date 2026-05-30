# 🏥 Sepsis Survival Prediction — Norwegian Hospital Data

> *Sepsis affects 1.7 million Americans annually and carries a 15-30% mortality rate. Early identification of high-risk patients is the single most effective intervention available. This project builds a machine learning pipeline to predict hospital survival outcomes from clinical data — prioritizing recall to minimize the cost of missing a high-risk patient.*

---

## 🧩 Clinical & Business Context

Sepsis is a life-threatening organ dysfunction caused by the body's extreme response to infection. It is one of the most expensive conditions treated in hospitals — the average sepsis hospitalization costs $18,000 to $24,000, and severe cases requiring ICU admission can exceed $100,000.

Two types of prediction errors carry very different costs in this 
context:

- **False negative** — model predicts survival, patient dies. Missed intervention opportunity, preventable death, liability risk
- **False positive** — model predicts non-survival, patient survives. Unnecessary ICU escalation, additional monitoring costs

In sepsis prediction, false negatives are far more costly than false positives. A missed high-risk patient loses the window for early intervention. An over-flagged patient receives additional monitoring that, while unnecessary, does no harm. This asymmetry drives all modeling decisions in this project because **recall is the primary evaluation metric.**

---

## 📊 Dataset

- **Source:** De-identified hospital data, Norwegian patients (2011 to 2012)
- **Records:** 110,204 unique patient episodes
- **Target:** Hospital outcome (0 = survived, 1 = deceased)
- **Features:** Age, sex, length of stay, number of sepsis episodes, number of ICD-10 diagnoses
- **Preprocessing:** 18 rows with missing ICD codes removed

---

## 🔍 Modeling Approach

Five classifier families were evaluated with and without class weighting to assess the tradeoff between accuracy and recall:

- Logistic Regression
- Decision Tree
- Random Forest
- Bagging Classifier
- Feedforward Neural Network

Class-weighted variants were tested to assess whether sacrificing accuracy for higher recall was necessary. The tuned unweighted models demonstrated that high recall and high accuracy are achievable simultaneously where weighted variants were ultimately unnecessary.

---

## 📈 Model Performance (Validation Set)

| Model | Accuracy | Recall | Precision | F1 |
|-------|----------|--------|-----------|-----|
| Logistic Regression | 92.62% | 92.62% | 88.55% | 89.27% |
| Decision Tree Tuned | 92.85% | 92.85% | 90.84% | 90.01% |
| Random Forest | 91.82% | 91.82% | 88.76% | 89.83% |
| Bagging Classifier | 91.58% | 91.58% | 88.59% | 89.71% |
| **Bagging Estimator Tuned** | **92.72%** | **92.72%** | **90.06%** | **89.92%** |
| Neural Network | 64.21% | 64.21% | 91.18% | 72.75% |

---

## ✅ Model Selection: Bagging Estimator Tuned

The Tuned Bagging Estimator was selected as the final model based on three criteria:

1. **Highest combined performance**

   - 92.72% accuracy and recall on the validation set, while 93.76% on training. Strong on both sets across all four metrics.

3. **Minimal overfitting**

   - the Tuned Bagging Estimator showed a 1.04% gap between training and validation accuracy, small enough to confirm the model generalizes well to new patients rather than memorizing the training data. Random Forest had a larger 3.14% gap, a sign of more overfitting. The Tuned Decision Tree is the one outlier worth noting. Its validation accuracy was actually slightly higher than its training accuracy, which almost never happens naturally. When a model performs better on data it has never seen than on data it was trained on, it usually means something went wrong in how the data was split rather than the model being genuinely that good. We treated it as a red flag and excluded it from final consideration despite its strong numbers. Lastly, the neural network, although having a near zero gap between training and validation, it performed a lot worse and didn't learn much at all, indicative of underfitting.

5. **Recall priority**

   - at 92.72% recall the model correctly identifies 92.72% of patients who will not survive, minimizing the higher-cost false negative error in a clinical setting.

---

## 🧠 SHAP Explainability

SHAP analysis was conducted on the default Bagging Classifier as an interpretability proxy for the tuned model. The tuned variant's randomized feature sampling introduces instability in SHAP attribution scores, making the default classifier a more appropriate vehicle for explaining feature importance while the tuned model handles prediction.

**Feature importance scores:**

| Feature | SHAP Importance |
|---------|----------------|
| Age | 0.38 |
| Length of Stay | 0.34 |
| Episode Number | 0.11 |
| Number of Medical Conditions | 0.10 |
| Sex | 0.07 |

Age and length of stay together account for **72% of predictive importance**, identifying them as the two primary clinical risk indicators for sepsis mortality. These findings align with established clinical literature on sepsis outcomes and provide a transparent, defensible basis for the model's predictions in a healthcare setting.

---

## ⚖️ Ethical & Clinical Considerations

1. **Recall optimization**

   - false negatives carry higher clinical and ethical cost than false positives in sepsis prediction. All modeling decisions prioritize minimizing missed high     risk patients over overall accuracy.

2. **Interpretability**

   - SHAP analysis ensures clinicians can understand and audit model predictions, supporting trust and adoption in clinical decision support contexts.

3. **Data handling**

   - dataset was fully anonymized and sourced from de-identified Norwegian hospital records compliant with ethical research standards.

4. **Limitations**

   - the model was trained on 2011 to 2012 Norwegian hospital data. Generalizability to other healthcare systems, patient populations, or treatment protocols       requires validation on independent datasets before clinical deployment.

---

## 📁 File Structure
