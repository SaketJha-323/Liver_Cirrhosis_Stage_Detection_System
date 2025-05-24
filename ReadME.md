# 🧬 Liver Cirrhosis Stage Detection Project

This project focuses on predicting the **histologic stage of liver cirrhosis** based on various medical and clinical indicators of a patient. Using a dataset from a **Mayo Clinic study on primary biliary cirrhosis (PBC)** conducted between **1974 and 1984**, machine learning models were trained to classify patients into one of **three stages of liver damage**:

- **Stage 1** → *Mild*  
- **Stage 2** → *Moderate*  
- **Stage 3** → *Severe*

---

## 📊 Key Highlights

- **Dataset Source:**  
  - Mayo Clinic study on **Primary Biliary Cirrhosis (PBC)**.
  - Period: 1974–1984.

- **Target Variable:**  
  - **Stage** of cirrhosis (1, 2, or 3).

- **Features Used:**  
  The dataset includes medical and biochemical attributes such as:

  - `N_Days`: Duration from registration to death/transplant/study end  
  - `Status`: Patient status – C (Censored), CL (Censored due to liver transplant), D (Death)  
  - `Drug`: Drug administered – D-penicillamine or placebo  
  - `Age`: Age in days  
  - `Sex`: M or F  
  - `Ascites`, `Hepatomegaly`, `Spiders`: Presence of medical symptoms (Y/N)  
  - `Edema`: Level of edema severity (N/S/Y)  
  - **Biochemical values**:  
    - `Bilirubin` (mg/dl), `Cholesterol` (mg/dl), `Albumin` (gm/dl), `Copper` (ug/day)  
    - `Alk_Phos` (U/l), `SGOT` (U/ml), `Triglycerides` (mg/dl)  
    - `Platelets` (per 1000 ml), `Prothrombin` time (sec)

---

## 🛠 Feature Engineering

- Converted categorical features (e.g., `Sex`, `Drug`, `Edema`, etc.) to numerical format.
- Handled missing data using appropriate imputation strategies.
- Normalized numerical features for improved model performance.

---

## 🤖 Models Evaluated

A range of classification models were evaluated using **StackingClassifier** with different meta (final) estimators:

- **Models Tested:**
  - `Logistic Regression` → **59.64% accuracy**
  - `SGD Classifier` → **58.38% accuracy**
  - `LDA` → **59.40% accuracy**
  - `Random Forest` → **94.76% accuracy**
  - `XGBoost` → **95.54% accuracy**
  - `SVM` → **84.16% accuracy**
  - `KNN` → **88.42% accuracy**
  - `Gaussian` → **50.54% accuracy**

- **Base Learners:**  
  - `RandomForestClassifier`  
  - `XGBClassifier`

- **Final Estimators Tested:**  
  - `SVC` → **95.90% accuracy**  
  - `LogisticRegression` → **95.74% accuracy**  
  - `SGDClassifier` → **95.64% accuracy**  
  - `LinearDiscriminantAnalysis` → **95.80% accuracy**  
  - `RandomForestClassifier` → **95.86% accuracy**  
  - `XGBClassifier` → **96.14% accuracy**

- **Final Estimator:**
  - `XGBClassifier` was chosen as the final meta-model due to its superior performance.

---

## 🧪 Prediction Results

- **Test 1:**  
  - **Input:** Synthetic random patient data  
  - **Output:**  
    - **Predicted Cirrhosis Stage:** `1` → *Stage 1 (Mild)*  
  - ✔️ Shows model is capable of detecting low-risk cases.

- **Test 2:**  
  - **Input:** Real sample from original dataset  
  - **Output:**  
    - **Predicted Cirrhosis Stage:** `3` → *Stage 3 (Severe)*  
  - ✔️ Confirms model can detect advanced liver damage from clinical data.

---

## 📌 Usage

- Input patient features (age, lab results, symptoms, etc.) in the required format.
- The model will output the predicted **stage of cirrhosis** with a corresponding **severity label**.
- Can assist medical professionals in early detection and prioritization of treatment.

### Python Version

- Python 3.12.5
