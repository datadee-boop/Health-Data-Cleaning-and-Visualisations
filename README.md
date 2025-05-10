# 🏥 Healthcare Data Cleaning Project

## 📌 Overview  
This project focuses on the cleaning and preprocessing of a healthcare dataset containing over **100,000 rows** of patient records. This large dataset mimics real-world scenarios commonly encountered in healthcare analytics, providing a comprehensive approach to handling and cleaning messy data.

The goal is to demonstrate how raw, unstructured data can be transformed into a clean, ready-to-analyze dataset.  
Cleaning steps include:
- Handling missing data  
- Normalizing categorical values  
- Converting date columns  
- Handling outliers  
- Splitting multi-valued columns  

---

## 🗃️ Dataset  
The dataset includes the following columns:

- `Patient_ID`: Unique identifier for each patient  
- `Gender`: Male, Female, or Other  
- `Age`: Patient's age  
- `Department`: Department (e.g., Oncology, Pediatrics)  
- `Diagnosis`: Medical condition (e.g., Diabetes, Cancer)  
- `Visit_Date`: Date of visit  
- `Discharge_Date`: Date of discharge  
- `Status`: Patient status (e.g., Discharged, In Treatment)  
- `Blood_Pressure`: e.g., 160/100  
- `Heart_Rate`: Heart rate value  
- `BMI`: Body Mass Index  
- `Smoker_Status`: Yes, No, Former  
- `Insurance_Type`: e.g., Private, Public  
- `Ethnicity`: Ethnic group  
- `Medication_Count`: Number of medications  
- `Length_of_Stay`: Derived from visit and discharge dates  

---

## 🛠️ Data Cleaning Process  

### 1. Patient ID  
- Removed prefix `"P"` (e.g., `P100000`)  
- Converted to integer  

### 2. Gender Normalization  
- Converted `"M"` → `"Male"`, `"F"` → `"Female"`  
- Preserved `"Other"`  

### 3. Age Validation  
- Removed invalid ages (`< 0` or `> 120`)  
- Flagged missing or outlier values  

### 4. Date Parsing  
- Converted `Visit_Date` and `Discharge_Date` to datetime format  
- Ensured `Discharge_Date` is after `Visit_Date`  

### 5. Categorical Normalization  
- Standardized case, spelling, and abbreviations in columns like `Department`, `Status`, `Smoker_Status`, `Ethnicity`  

### 6. Blood Pressure Parsing  
- Split `Blood_Pressure` into `Systolic_Bp` and `Diastolic_Bp`  
- Converted to numeric  

### 7. Heart Rate Validation  
- Flagged implausible values (> 250 bpm or < 30 bpm)  

### 8. BMI Handling  
- Replaced negative or extreme values with `NaN`  

### 9. Ethnicity Normalization  
- Cleaned and standardized entries (e.g., `"W"` → `"White"`)  

### 10. Medication Count Validation  
- Ensured numeric, non-negative integers  

### 11. Length of Stay  
- Recalculated as `Discharge_Date - Visit_Date`  
- Ensured positive durations  

### 12. Duplicate Removal  
- Removed duplicate records  

### 13. Final Validation  
- Checked for missing values  
- Ensured consistent data types and cleaned values  

---

## ✅ Conclusion  
With over **100,000 rows**, this healthcare dataset was successfully cleaned and preprocessed, transforming it from raw, inconsistent data into a structured and reliable resource for analysis.

This project demonstrates essential techniques in data cleaning, an indispensable step for any successful data analytics pipeline.

---

## 🧰 Technologies Used  
- Python  
  - `pandas`  
  - `numpy`  
- Data Cleaning & Preprocessing Techniques  
- Date and String Manipulation  
- Categorical Data Normalization  

---

## 👤 Author  
**DataDee-Boop**  
Aspiring data analyst passionate about healthcare analytics and making messy data beautiful.
