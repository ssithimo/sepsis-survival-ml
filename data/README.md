# Data Description 📊

This folder contains the dataset used for the Sepsis Survival Prediction Project.

---

## 🗂️ Dataset Overview

- **Source:** Norwegian hospitals, collected between 2011 and 2012  
- **Number of Records:** 110,204 patient encounters related to sepsis  
- **Purpose:** To analyze sepsis patient outcomes and predict survival status after hospitalization

---

## 🧩 Features Included

| Feature Name       | Description                                                                                 |
|--------------------|---------------------------------------------------------------------------------------------|
| **Age**            | Patient's age in years                                                                      |
| **Sex**            | Patient sex (0 = Male, 1 = Female)                                                         |
| **Length of Stay** | Duration of hospital stay (in days)                                                        |
| **Hospital Outcome**| Patient outcome after hospitalization (0 = Alive, 1 = Deceased)                             |
| **Episode Number**  | Number of sepsis-related hospital admissions for the patient                               |
| **ICD-10 Codes**   | International Classification of Diseases codes representing patient's medical conditions    |

---

## ⚠️ Data Cleaning Notes

- There were 18 missing ICD-10 codes, which were dropped due to their negligible impact on the large dataset.  
- For modeling, ICD-10 codes were summarized into a count of medical conditions per patient.  
- Data anonymized to protect patient privacy.
