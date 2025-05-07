# Healthcare Data Cleaning Project

## Overview
This project focuses on the cleaning and preprocessing of a healthcare dataset containing over **100,000 rows** of patient records. This large dataset mimics real-world data scenarios commonly encountered in healthcare analytics, providing a comprehensive approach to handling and cleaning large, messy datasets. The goal of this project is to demonstrate the process of transforming raw, unstructured data into a clean and ready-to-analyze dataset. The cleaning steps include handling missing data, normalizing categorical values, converting date columns, handling outliers, and splitting multi-valued columns into separate attributes.

## Dataset
The dataset used in this project contains the following columns:
- **Patient_ID**: Unique identifier for each patient.
- **Gender**: Gender of the patient (Male, Female, Other).
- **Age**: Age of the patient.
- **Department**: Department in which the patient was treated (e.g., Oncology, Pediatrics).
- **Diagnosis**: Medical condition diagnosed (e.g., Diabetes, Cancer).
- **Visit_Date**: Date of the patient's visit.
- **Discharge_Date**: Date the patient was discharged.
- **Status**: Current status of the patient (e.g., Discharged, In Treatment).
- **Blood_Pressure**: Blood pressure measurement (e.g., 160/100).
- **Heart_Rate**: Heart rate of the patient.
- **BMI**: Body Mass Index.
- **Smoker_Status**: Whether the patient is a smoker (Yes, No, Former).
- **Insurance_Type**: Type of insurance (e.g., Private, Public).
- **Ethnicity**: Ethnic group of the patient.
- **Medication_Count**: Number of medications prescribed to the patient.
- **Length_of_Stay**: Duration of stay (calculated as the difference between Discharge and Visit dates).

With **over 100,000 rows**, the dataset simulates real-life healthcare data, providing a rich environment for practicing data cleaning techniques on a scale commonly encountered in the industry.

## Data Cleaning Process

### 1. **Handling Patient ID**
   - The **Patient_ID** column originally contained a prefix "P" (e.g., "P100000"). This was removed, and the column was converted into an integer type for easier analysis.

### 2. **Gender Normalization**
   - The **Gender** column contained inconsistent abbreviations ("M" for Male, "F" for Female). These values were standardized into full forms: "Male" and "Female". The "Other" category was preserved as is.

### 3. **Age Validation**
   - Invalid ages (e.g., negative values or ages above 120) were identified and removed.
   - Missing values (NaN) in the **Age** column were flagged for further investigation or imputation.

### 4. **Date Parsing**
   - **Visit_Date** and **Discharge_Date** columns were converted to the `datetime` format using the `pd.to_datetime()` function, with invalid dates coerced to `NaT`.
   - Discrepancies were addressed where **Discharge_Date** occurred before **Visit_Date**. These records were updated by setting the **Discharge_Date** to the corresponding **Visit_Date** for consistency.

### 5. **Categorical Column Normalization**
   - **Gender**, **Department**, **Diagnosis**, **Status**, **Smoker_Status**, **Insurance_Type**, and **Ethnicity** columns were checked for consistency and standardized. 
   - Minor discrepancies such as inconsistent casing or abbreviations (e.g., "W" for "White" ethnicity) were resolved.

### 6. **Blood Pressure Parsing**
   - The **Blood_Pressure** column, formatted as "Systolic/Diastolic", was split into two separate columns: **Systolic_Bp** and **Diastolic_Bp**. 
   - Both columns were converted to numeric types for further analysis.

### 7. **Heart Rate Outlier Detection**
   - A check for unrealistic values, such as a **Heart_Rate** of "300", was conducted. Suspicious entries were flagged for further validation.

### 8. **BMI Handling**
   - Negative BMI values were converted to `NaN` as they were not valid.
   - The **BMI** column was checked for logical consistency and cleaned accordingly.

### 9. **Ethnicity Normalization**
   - The **Ethnicity** column was standardized to ensure that all categories were correctly labeled (e.g., "W" was changed to "White").

### 10. **Medication Count Validation**
   - The **Medication_Count** column was checked for non-positive integer values. Inconsistent entries were handled.

### 11. **Length of Stay Calculation**
   - The **Length_of_Stay** was recalculated as the difference between **Discharge_Date** and **Visit_Date**.
   - Any negative values in this column (which may have resulted from previous inconsistencies) were corrected.

### 12. **Handling Duplicates**
   - Duplicate records were checked for and removed to ensure a clean dataset.

### 13. **Final Validation**
   - After applying the transformations, all columns were rechecked for consistency, invalid values, and missing data. The cleaned dataset was then ready for analysis.

## Conclusion
The healthcare dataset, consisting of over **100,000 rows**, was successfully cleaned and preprocessed, transforming it from a raw, inconsistent state into a structured, reliable dataset. This project demonstrates a comprehensive approach to data cleaning on a large dataset, handling a wide variety of common data issues found in real-life scenarios. The dataset is now ready for further analysis, including statistical analysis, predictive modeling, or data visualization.

## Technologies Used
- Python (Pandas, NumPy)
- Data Cleaning and Preprocessing Techniques
- Date and String Handling
- Categorical Data Normalization

## Author
This project was completed by **DataDee-Boop**, an aspiring data analyst passionate about healthcare analytics and data preprocessing.

