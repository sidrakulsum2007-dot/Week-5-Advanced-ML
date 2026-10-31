# Student Pass/Fail Prediction System – Week 5

## Project Overview
This project uses Machine Learning classification algorithms to predict whether a student is likely to pass or fail based on academic performance, study habits and other student-related information.

## Objectives
- Build a student Pass/Fail prediction system.
- Apply Random Forest, KNN and SVM algorithms.
- Compare model performance.
- Perform hyperparameter tuning using GridSearchCV.
- Identify important features.
- Generate student result predictions.

## Dataset
- Dataset: Student Performance (`student-mat.csv`)
- Total records: 395
- Original features: 33
- Pass: 265 students
- Fail: 130 students

**Target rule:** G3 ≥ 10 = Pass (1); G3 < 10 = Fail (0).

G3 was excluded from the input features to prevent target leakage. G1 and G2 were retained, so the model uses previous examination marks to predict the final result.

## Algorithms Used
1. Random Forest Classifier
2. K-Nearest Neighbors (KNN)
3. Support Vector Machine (SVM)

## Model Performance

| Model | Accuracy | Precision | Recall | F1 Score |
|---|---:|---:|---:|---:|
| Random Forest | 87.3% | 95.7% | 84.9% | 90.0% |
| KNN | 77.2