<div align="center">

# Heart Stroke Prediction

![Python](https://img.shields.io/badge/Python-3.8%2B-3776AB?style=flat-square&logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=flat-square&logo=jupyter&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-F7931E?style=flat-square&logo=scikit-learn&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-22C55E?style=flat-square)

A supervised machine learning project that predicts the risk of a heart stroke based on patient clinical and demographic data. Four classification models are trained and evaluated to identify the most effective approach for early stroke detection.

</div>

---

## Table of Contents

- [Overview](#overview)
- [Dataset](#dataset)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Methodology](#methodology)
- [Results](#results)
- [Key Findings](#key-findings)
- [Future Work](#future-work)
- [License](#license)
- [Contact](#contact)

---

## Overview

Stroke is the second leading cause of death worldwide. This project applies machine learning to healthcare data to predict whether a patient is likely to have a stroke, enabling earlier clinical intervention. The full pipeline covers data preprocessing, exploratory analysis, model training, and comparative evaluation.

---

## Dataset

**Source:** [Kaggle — Stroke Prediction Dataset by fedesoriano](https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset)  
**Records:** 5,110 patients | **Features:** 10 input variables + 1 target

| Feature | Type | Description |
|---|---|---|
| `gender` | Categorical | Male, Female, or Other |
| `age` | Numerical | Age of the patient |
| `hypertension` | Binary | 1 = Has hypertension |
| `heart_disease` | Binary | 1 = Has heart disease |
| `ever_married` | Categorical | Yes / No |
| `work_type` | Categorical | Private, Self-employed, Govt_job, Children, Never_worked |
| `Residence_type` | Categorical | Urban / Rural |
| `avg_glucose_level` | Numerical | Average blood glucose level (mg/dL) |
| `bmi` | Numerical | Body Mass Index |
| `smoking_status` | Categorical | Formerly smoked / Never smoked / Smokes / Unknown |
| `stroke` | **Target** | 1 = Had a stroke, 0 = Did not |

---

## Project Structure

```
heart-stroke-prediction/
├── Stroke_detection.ipynb             # Main notebook — full pipeline
├── healthcare-dataset-stroke-data.csv # Dataset (download from Kaggle)
├── requirements.txt                   # Python dependencies
└── README.md
```

---

## Installation

**Prerequisites:** Python 3.8+, pip

```bash
# Clone the repository
git clone https://github.com/your-username/heart-stroke-prediction.git
cd heart-stroke-prediction

# Install dependencies
pip install -r requirements.txt

# Launch the notebook
jupyter notebook Stroke_detection.ipynb
```

Download the dataset from [Kaggle](https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset) and place `healthcare-dataset-stroke-data.csv` in the project root before running.

---

## Methodology

**1. Data Preprocessing**
- Removed the `id` column (no predictive value)
- Imputed missing `bmi` values using the column mode
- Label-encoded all categorical variables numerically
- Binned continuous `age` into five groups: Child (0–12), Teen (13–19), Young Adult (20–30), Adult (31–60), Senior (61–100)
- Applied an 80/20 train/test split (`random_state=42`)

**2. Exploratory Data Analysis**
- Correlation analysis across all features vs. stroke outcome
- Annotated heatmap of the full correlation matrix
- 16 count plots and line plots covering age, gender, BMI, glucose, smoking, work type, and residence

**3. Models Trained**
- Logistic Regression
- Support Vector Machine (SVM)
- Decision Tree Classifier
- K-Nearest Neighbors (KNN)

**4. Evaluation Metrics**
- Accuracy Score, F1 Score, Mean Absolute Error, Mean Squared Error, Log Loss, Confusion Matrix

---

## Results

| Model | Accuracy |
|---|---|
| Logistic Regression | **93.8%** |
| Support Vector Machine | **93.8%** |
| K-Nearest Neighbors | **93.8%** |
| Decision Tree | 91.8% |

Logistic Regression, SVM, and KNN all converge at ~93.8% accuracy. Logistic Regression is the recommended choice for any clinical deployment scenario due to its interpretability.

---

## Key Findings

- **Age** is the strongest predictor of stroke risk, with the 61–100 group showing the highest incidence.
- Patients with **hypertension** and **heart disease** are at elevated risk, though stroke also occurs in patients without either — suggesting these features alone are insufficient.
- **BMI in the 20–50 range** correlates with higher stroke likelihood.
- Non-smokers showed higher stroke rates than smokers in this dataset, likely due to class imbalance or confounding variables — warranting further investigation.
- **Marital status**, **work type**, and **residence type** each carry moderate predictive signal.

---

## Future Work

- Handle class imbalance using SMOTE or weighted classes
- Explore ensemble models (Random Forest, XGBoost) for improved performance
- Hyperparameter tuning via GridSearchCV
- Deploy as an interactive web application using Streamlit
- Incorporate SHAP values for model explainability

---

## License

This project is licensed under the [MIT License](LICENSE).

---

## Contact

**Jan Sher Khan Nizamani**  
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/jan-sher-khan-nizamani-2212353b7/)
