# CardioRiskIQ Project – Personal Documentation  
### **Author:** Jackie CW Vescio  
### **Track:** Advanced  
### **Project:** Cleveland Heart Disease Dataset Analysis  
---

## Purpose of This Document
This README serves as my **personal project documentation** for the CardioRiskIQ heart-disease prediction project. It contains:

- A clear data dictionary  
- Clinical interpretation notes for model explainability  
- Explanation of the `num` target (multi-class and binary formats)  
- Additional insights that support, but do not clutter, my Jupyter notebooks  

This document helps maintain clean notebooks while preserving essential context
for feature engineering, modeling, and final report writing.

---

# 1. Data Dictionary – Cleveland Heart Disease Dataset

The table below describes each feature, including its clinical meaning and potential relevance to cardiac risk.

| Column Name | Description | Type | Clinical Meaning |
|------------|-------------|------|------------------|
| **id** | Patient identifier | Numeric | Unique ID, not predictive. |
| **age** | Age in years | Numeric | Older age increases heart disease risk. |
| **sex** | Biological sex (`Male`, `Female`) | Categorical | Males generally have higher baseline risk. |
| **dataset** | Source dataset (e.g., `Cleveland`) | Categorical | Reference only; not clinically meaningful. |
| **cp** | Chest pain type | Categorical | Indicates angina type. Very informative clinically. |
| **trestbps** | Resting blood pressure (mm Hg) | Numeric | Higher BP increases risk via arterial strain. |
| **chol** | Serum cholesterol (mg/dl) | Numeric | High cholesterol contributes to plaque buildup. |
| **fbs** | Fasting blood sugar > 120 mg/dl (`True`/`False`) | Boolean | Indicator of diabetes; major cardiac risk factor. |
| **restecg** | Resting ECG results | Categorical | Detects LVH, ischemia, or normal rhythm. |
| **thalch** | Max heart rate achieved during exercise | Numeric | Lower values may indicate reduced cardiac capacity. |
| **exang** | Exercise-induced angina (`True`/`False`) | Boolean | Strong indicator of coronary blockage. |
| **oldpeak** | ST depression induced by exercise | Numeric | Elevated values suggest ischemia or stress abnormalities. |
| **slope** | Slope of the ST segment during peak exercise | Categorical | Flat/downsloping slopes correlate with heart disease. |
| **ca** | Number of major vessels visualized (0–3) | Numeric | One of the strongest predictors of disease severity. |
| **thal** | Thallium stress test result | Categorical | Indicates blood flow patterns; abnormal results indicate ischemia. |
| **num** | Target variable (0–4) | Target | 0 = no disease; 1–4 increasing severity. |

---

# 2. Understanding the Target Variable (`num`)

The `num` column represents **diagnosed heart disease severity**, and is used as our target in modeling:

- `0` → No heart disease  
- `1` → Mild  
- `2` → Moderate  
- `3` → Moderate-to-severe  
- `4` → Severe  

Depending on project direction, we may:

### **Model it as multi-class (0–4)**  
Useful for risk stratification.

### **Convert it to binary for simpler classification**  
(0 = no disease, 1 = disease)

\[
\text{num\_binary} = 
\begin{cases}
0 & \text{if } num = 0 \\
1 & \text{if } num > 0
\end{cases}
\]

This conversion is common in clinical ML projects where the question is:
**“Does this patient have heart disease or not?”**

This README preserves both interpretations for clarity.

---

# 3. Clinical Interpretation Cheat Sheet  
*(Used later for explainability, SHAP values, and model interpretation.)*

Understanding what each feature represents clinically helps explain *why* a model behaves the way it does.

### **Age**
- Strong predictor; risk increases with age.

### **Sex**
- Males have higher early-life risk; differences narrow with age.

### **Chest Pain Type (cp)**
- **Typical angina** is highly predictive of coronary artery disease.
- **Asymptomatic** cases often correlate with silent ischemia.

### **Resting BP (trestbps)**
- High blood pressure stresses arteries and increases risk.

### **Cholesterol (chol)**
- High cholesterol → higher plaque buildup.

### **Fasting Blood Sugar (fbs)**
- High values suggest diabetes, a major cardiovascular risk factor.

### **Resting ECG (restecg)**
- **Left ventricular hypertrophy** and **ST-T abnormalities** often indicate underlying disease.

### **Max Heart Rate (thalch)**
- Lower exercise capacity → reduced cardiac function.

### **Exercise-Induced Angina (exang)**
- Symptom triggered by exertion strongly suggests coronary obstruction.

### **ST Depression (oldpeak)**
- Major clinical marker of ischemia.

### **Slope of ST Segment (slope)**
- Flat/downsloping responses are linked to higher risk.

### **Number of Vessels Colored (ca)**
- Direct measure of arterial blockage — one of the strongest predictors.

### **Thalium Test Result (thal)**
- Identifies normal, fixed, or reversible perfusion defects.

---

# 4. How to Use This README With My Notebook

This README provides:
- extended explanations  
- clinical domain notes  
- narrative context  

My **Jupyter notebook** focuses on:
- code execution  
- data inspection  
- visualizations  
- EDA results  

Keeping them separate ensures both documents stay readable and organized.

---

# 5. Notes for Future Steps (Non-technical)

- Week 1: Complete EDA and documentation   
- Week 2: Feature engineering and preprocessing  
- Week 3: Model development (ML and/or DL)  
- Week 4: Optimization + interpretability  
- Week 5: Deployment (Streamlit or API)  

I will update this README as the project progresses.

---


