# Healthcare Readmission Prediction using Machine Learning

## Project Overview
This project predicts whether a patient will be readmitted to the hospital based on historical patient data and hospital records. It helps healthcare providers to reduce unnecessary readmissions, improve patient care, and optimize resource allocation.

---

## Dataset
The dataset contains patient-level information:

| Column Name       | Description                                   |
|------------------|-----------------------------------------------|
| PatientID        | Unique patient identifier (dropped for model)|
| Age              | Age group of the patient                      |
| Gender           | Male/Female                                   |
| AdmissionType    | Emergency, Elective, etc.                     |
| Diagnosis        | Type of disease (Diabetes, Heart, Cancer, Infection) |
| NumMedications   | Number of medications prescribed             |
| NumProcedures    | Number of procedures performed               |
| Readmitted       | Target variable (Yes/No)                     |

*Note: For demonstration, a small sample dataset of 20 patients is used. In real-world projects, larger datasets with thousands of rows should be used.*

---

## Problem Statement
Hospital readmissions are costly and can indicate poor quality of care. Predicting readmission allows hospitals to:
- Plan follow-ups
- Allocate resources efficiently
- Reduce patient risk

---

## Data Preprocessing
1. **Drop ID Column**  
   - `PatientID` is unique and not predictive → dropped.

2. **Handle Categorical Variables**  
   - Used `LabelEncoder` to convert text categories into numeric format.  
   - Columns encoded: `Age`, `Gender`, `AdmissionType`, `Diagnosis`, `Readmitted`.

3. **Feature Scaling**  
   - Used `StandardScaler` to scale features for Logistic Regression.

4. **Train-Test Split**  
   - Split data: 80% training, 20% testing.

---

## Machine Learning Models
1. **Logistic Regression**  
   - Predicts probability of readmission (binary classification).  
   - Simple, interpretable, works well for linearly separable data.

2. **Random Forest Classifier**  
   - Ensemble of decision trees for robust prediction.  
   - Handles non-linear relationships, less prone to overfitting.

---

## Model Training & Prediction
- Split dataset into `X_train`, `X_test`, `y_train`, `y_test`.
- Trained both Logistic Regression and Random Forest models.
- Predicted readmission on test data.

---

## Model Evaluation
Metrics used:
- Accuracy
- Confusion Matrix
- Precision, Recall, F1-Score

Sample output for small dataset:

**Logistic Regression**  
Accuracy: 1.0
Classification Report:
precision recall f1-score support
0 1.00 1.00 1.00 2
1 1.00 1.00 1.00 2
Confusion Matrix:
[[2 0]
[0 2]]


**Random Forest**  
Accuracy: 1.0
Classification Report:
precision recall f1-score support
0 1.00 1.00 1.00 2
1 1.00 1.00 1.00 2
Confusion Matrix:
[[2 0]
[0 2]]
