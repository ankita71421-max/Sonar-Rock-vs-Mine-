# Sonar Rock vs Mine Prediction

A machine learning project that predicts whether an object detected by sonar is a **Rock (R)** or a **Mine (M)** using sonar signal data.

## Project Overview

This project uses the Sonar dataset, which contains 208 samples and 60 numerical features representing sonar signal measurements.

The project compares multiple machine learning classification models and evaluates their performance using test-set metrics and 5-fold stratified cross-validation.

The models used are:

- Logistic Regression
- K-Nearest Neighbors (KNN)
- Decision Tree
- Random Forest

After evaluation, Random Forest was selected as the final model for prediction.

## Dataset

The dataset contains:

- 208 samples
- 60 numerical input features
- 1 target column
- Two classes:
  - `M` - Mine
  - `R` - Rock

The dataset is stored in:

`sonar.csv`

## Machine Learning Process

The project follows these steps:

1. Load the Sonar dataset
2. Explore the dataset
3. Separate features and target
4. Split the data into training and testing sets
5. Train multiple classification models
6. Evaluate models using:
   - Accuracy
   - Precision
   - Recall
   - F1 Score
7. Perform 5-fold stratified cross-validation
8. Compare model performance
9. Train the final Random Forest model on the complete dataset
10. Use the trained model for Rock/Mine prediction

## Models

### Logistic Regression

Used as a linear classification model and evaluated using the same performance metrics as the other models.

### K-Nearest Neighbors

Classifies a sample based on the nearest training samples after feature scaling.

### Decision Tree

Uses decision rules based on feature values to classify the sonar signal.

### Random Forest

Uses multiple decision trees and combines their predictions to perform classification.

The final Random Forest model uses:

- `n_estimators = 100`
- `random_state = 1`

## Model Evaluation

### Test Set Results

| Model | Accuracy | Precision | Recall | F1 Score |
|---|---:|---:|---:|---:|
| Logistic Regression | 66.67% | 72.22% | 59.09% | 65.00% |
| KNN | 80.95% | 76.92% | 90.91% | 83.33% |
| Decision Tree | 78.57% | 88.24% | 68.18% | 76.92% |
| Random Forest | 80.95% | 79.17% | 86.36% | 82.61% |

### 5-Fold Stratified Cross-Validation

| Model | Mean Accuracy | Standard Deviation |
|---|---:|---:|
| Logistic Regression | 76.47% | 3.69% |
| KNN | 79.30% | 4.53% |
| Decision Tree | 73.08% | 4.71% |
| Random Forest | 79.35% | 3.79% |

Random Forest was selected as the final model based on the overall evaluation performed in this project.

## Prediction

The project includes an interactive prediction function where the user can enter 60 sonar values separated by commas.

The model returns:

- Predicted class: Rock or Mine
- Mine probability
- Rock probability

The trained model is saved as:

`sonar_random_forest.pkl`

## Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn
- Joblib
- Google Colab
- Jupyter Notebook

## Project Files

```text
Sonar-Rock-Mine-Prediction/
│
├── README.md
├── Rock_vs_Mine_Prediction.ipynb
├── sonar.csv
└── sonar_random_forest.pkl