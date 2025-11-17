# Pediatric TBI Risk Prediction Using Clinical Data and Radiology Text

This project uses the **PECARN pediatric head trauma dataset (43,399 records)** to study traumatic brain injury (TBI) risk in children.  
We combine **clinical variables** and **radiology report text** to explore how well we can classify patients into risk levels for clinically-important brain injury. :contentReference[oaicite:1]{index=1}

---

## 🩺 Project Background

Head trauma is a common reason for pediatric emergency visits. CT scans are useful for detecting TBI, but they expose children to radiation.  
The goal is to use reliable clinical indicators and radiology language to help identify which children are at higher risk and may need urgent imaging. :contentReference[oaicite:2]{index=2}

---

## 📊 Data & Variables (Cleaned Dataset)

The original PECARN dataset was large and messy, so we performed careful **data wrangling**:

- Confirmed the dataset size: **43,399 patient records**
- Removed records missing critical variables (e.g., CT result, GCS score)
- Standardized formats (e.g., converted “yes/no” to 1/0, made GCS numeric)
- Kept only variables needed for our models and analyses :contentReference[oaicite:3]{index=3}

Final core variables include (simplified):

- `gcs_score` – Glasgow Coma Scale
- `neuro_deficit` – neurological symptoms (yes/no)
- `vomiting` – vomiting (yes/no)
- `loss_consciousness` – loss of consciousness
- `mechanism_of_injury` – how the injury occurred
- `ct_received` – CT done or not
- `radiology_note` – free-text radiology report :contentReference[oaicite:4]{index=4}

---

## 🔤 Text (NLP) Processing

Radiology notes are **free text**, so we:

- Lowercased all text
- Removed punctuation and stopwords
- Tokenized into words
- Created features from important words and entities related to hemorrhage, fractures, and normal findings :contentReference[oaicite:5]{index=5}

These text features were then used in the risk classification model.

---

## 🤖 Modeling & Analysis

We analyzed **TBI risk levels** using both structured features and text-derived features.

Key steps:

1. Visualized the **distribution of risk levels** (high, moderate, low, unknown)
2. Trained a classification model to predict risk levels
3. Examined **feature importance**:
   - Hemorrhage-related entities (especially subdural/unspecified hemorrhage) were strong predictors
   - Fracture types and “normal study” findings were also important :contentReference[oaicite:6]{index=6}
4. Evaluated performance using a **confusion matrix**:
   - Good performance for “high”, “moderate”, and “unknown”
   - Lower performance for “low” risk, which suggests more refinement is needed :contentReference[oaicite:7]{index=7}

---

## ✅ Conclusion

This project shows that combining:

- **Structured clinical data** (GCS, symptoms, mechanism)
- **Radiology-note language features**

can help classify pediatric TBI risk and highlight which findings are most informative.  
It also demonstrates how critical **data wrangling** and **careful preprocessing** are in a real-world health informatics workflow. :contentReference[oaicite:8]{index=8}

---

## 📂 Files in This Repository

- `project report.docx` – Full written report describing the project
- `README.md` – Short overview (this file)
- Notebooks / code – (to be added): loading data, wrangling, NLP, modeling, and evaluation

---

## 🔒 Data Note

The original PECARN dataset is not included in this repository.  
Any shared data or examples should be **synthetic or de-identified**.
