# Week 5 – Advanced Machine Learning
## Student Pass/Fail Prediction System

### 1. Introduction
This project focuses on developing a Student Pass/Fail Prediction System using Machine Learning classification algorithms. The system predicts whether a student is likely to pass or fail based on academic performance, study habits, family background and other student-related information.

### 2. Objective
- Understand and apply classification algorithms.
- Train multiple machine learning models.
- Compare model performance using evaluation metrics.
- Perform hyperparameter tuning.
- Identify important features influencing student performance.
- Generate Pass/Fail predictions.

### 3. Dataset Description
The project uses the Student Performance dataset (`student-mat.csv`).

- Total records: 395
- Original features: 33 columns
- Target variable: Result

The target variable was created using the final grade (G3):
- Pass (1): G3 greater than or equal to 10.
- Fail (0): G3 below 10.

The dataset contains 265 Pass records and 130 Fail records.

### 4. Data Preprocessing
The following preprocessing techniques were applied:

- Separated input features and target variable.
- Excluded G3 from input features to prevent target leakage.
- Converted categorical variables using OneHotEncoder.
- Scaled numerical variables using StandardScaler.
- Divided the dataset into 80% training data and 20% testing data.
- Used stratified splitting to preserve class proportions.

### 5. Machine Learning Algorithms
Three classification algorithms were implemented:

**Random Forest Classifier:** Combines multiple decision trees to improve prediction performance.

**K-Nearest Neighbors (KNN):** Predicts results by comparing students with similar data.

**Support Vector Machine (SVM):** Finds a decision boundary to separate Pass and Fail categories.

### 6. Model Performance Comparison

| Model | Accuracy | Precision | Recall | F1 Score |
|---|---:|---:|---:|---:|
| Random Forest | 87.3% | 95.7% | 84.9% | 90.0% |
| KNN | 77.2% | 81.8% | 84.9% | 83.3% |
| SVM | 86.1% | 92.0% | 86.8% | 89.3% |

Random Forest achieved the highest test accuracy and F1-score among the three models.

### 7. Hyperparameter Tuning
GridSearchCV with 5-fold cross-validation was used to tune the Random Forest model.

Best parameters:
- Number of estimators: 200
- Maximum depth: 10
- Minimum samples split: 5

Best cross-validation F1-score: 94.3%.

The tuned model achieved the following test results:
- Accuracy: 87.3%
- Precision: 95.7%
- Recall: 84.9%
- F1-score: 90.0%

The tuned model did not improve the held-out test scores compared with the original Random Forest model.

### 8. Confusion Matrix Analysis
The Random Forest confusion matrix produced these results:

- True Negatives: 24
- False Positives: 2
- False Negatives: 8
- True Positives: 45

Out of 79 test records, 69 predictions were correct.

### 9. Feature Importance Analysis
The feature importance visualization identified the following important features:

1. G2 – Second-period grades
2. G1 – First-period grades
3. Previous failures
4. Absences
5. Going out frequency

Previous examination grades had the strongest influence on the model's predictions.

### 10. Prediction Results
The trained Random Forest model was used to generate Pass/Fail predictions for test records. Actual and predicted results were stored in `prediction_results.csv`.

### 11. Tools and Technologies Used
- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook
- Visual Studio Code

### 12. Conclusion
The Student Pass/Fail Prediction System successfully demonstrates the application of machine learning classification algorithms.

Among the three models, Random Forest achieved the best overall test performance with 87.3% accuracy and a 90% F1-score. Hyperparameter tuning was also performed to improve model configuration.

This project provided practical experience in data preprocessing, classification, model evaluation, hyperparameter tuning, feature importance analysis and prediction generation.

**Note:** This is an educational prediction project. Its predictions should not be treated as definitive judgments about individual students.