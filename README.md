# 🌍 Environmental Management & Pollution Control – Week 2  

## 📌 Project Theme  
This project is part of the **Edunet AI Internship** under the theme *Environmental Management & Pollution Control*.  
The aim is to analyze **river water quality data** from CPCB (Central Pollution Control Board) and classify water quality into categories such as **Good, Moderate, or Poor** using machine learning.  

---

## 📊 Dataset  
- **Source**: CPCB (Central Pollution Control Board) – River Water Quality Data 2022  
- **Format**: Originally PDF → converted to Excel → cleaned into `cleaned_data.csv`.  
- **Structure**:  
  - First three columns → `Station Code`, `Monitoring Location`, `State Name`  
  - Parameters (each with MIN/MAX, then averaged):  
    - Dissolved Oxygen (mg/L)  
    - Bio-Chemical Oxygen Demand (BOD, mg/L)  
    - pH  
    - Nitrate (mg/L)  
    - Total Coliform (MPN/100mL)  
    - *(Fecal Streptococci excluded due to too many missing values)*  

---

## ✅ Week-2 Work: Preprocessing + Model Training  

### 🔹 1. Preprocessing  
- Created **AVG columns** for parameters (average of MIN & MAX).  
- Converted `BDL` (Below Detection Limit) → NaN → filled with column mean.  
- Selected CPCB-relevant features:  
  - `Dissolved Oxygen AVG`  
  - `Bio-Chemical Oxygen Demand AVG`  
  - `pH AVG`  
  - `Nitrate AVG`  
  - `Total Coliform AVG`  

### 🔹 2. Label Creation  
Defined a target column `Water_Quality_Class` using CPCB thresholds:  
- **Good** → DO ≥ 6, BOD ≤ 2, 6.5 ≤ pH ≤ 8.5, Coliform ≤ 500.  
- **Moderate** → DO ≥ 4, BOD ≤ 3, pH between 6–9, Coliform ≤ 2500.  
- **Poor** → Otherwise.  

### 🔹 3. Model Training  
- Train/Test split (80/20), scaled features.  
- Trained two models:  
  - Logistic Regression (baseline).  
  - Random Forest Classifier (better performance).  

### 🔹 4. Evaluation  
- Metrics: Accuracy, Precision, Recall, F1-score.  
- Confusion Matrix (classification results).  
- Feature Importance (which parameters affect quality most).  

---


