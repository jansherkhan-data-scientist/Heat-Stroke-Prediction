# 🧠 Heart Stroke Prediction using Machine Learning

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![scikit-learn](https://img.shields.io/badge/scikit--learn-1.2+-orange.svg)
![Pandas](https://img.shields.io/badge/Pandas-1.5+-green.svg)
![License](https://img.shields.io/badge/License-MIT-red.svg)

## 📋 Project Overview

This project focuses on predicting the likelihood of a heart stroke in patients using various machine learning algorithms. The analysis is performed on a healthcare dataset containing patient information including demographic details, medical history, and lifestyle factors.

### 🎯 Objective
To develop and compare multiple machine learning models that can accurately predict whether a patient is at risk of suffering a heart stroke based on their health parameters.

## 📊 Dataset

The dataset (`healthcare-dataset-stroke-data.csv`) contains **5,110 patient records** with the following features:

| Feature | Description |
|---------|-------------|
| `id` | Unique patient identifier |
| `gender` | Male, Female, or Other |
| `age` | Age of the patient (years) |
| `hypertension` | 0 = No hypertension, 1 = Has hypertension |
| `heart_disease` | 0 = No heart disease, 1 = Has heart disease |
| `ever_married` | Yes or No |
| `work_type` | Type of employment |
| `Residence_type` | Urban or Rural |
| `avg_glucose_level` | Average glucose level in blood |
| `bmi` | Body Mass Index |
| `smoking_status` | Smoking history |
| `stroke` | **Target variable:** 0 = No stroke, 1 = Stroke |

## 🔧 Data Preprocessing

The following preprocessing steps were performed:

1. **Handling Missing Values**
   - BMI column had 201 missing values → filled with mode

2. **Feature Encoding**
   - Converted categorical variables to numerical values:
     - Gender: Male→1, Female→0, Other→2
     - Ever married: Yes→1, No→0
     - Residence type: Urban→1, Rural→0
     - Smoking status: formerly smoked→0, never smoked→1, smokes→2, Unknown→3
     - Work type: Private→0, Self-employed→1, children→2, Govt_job→3, Never_worked→4

3. **Age Binning**
   - Categorized age into groups:
     - 0: 0-12 years
     - 1: 13-19 years
     - 2: 20-30 years
     - 3: 31-60 years
     - 4: 61-100 years

## 🤖 Machine Learning Models Implemented

| Model | Accuracy | F1 Score |
|-------|----------|----------|
| **Logistic Regression** | 93.93% | 0.00 |
| **Support Vector Machine (SVM)** | 93.93% | 0.00 |
| **K-Nearest Neighbors (KNN)** | 93.74% | 0.00 |
| **Decision Tree Classifier** | 90.99% | 0.25 |

> **Note:** Low F1 scores indicate class imbalance in the dataset (only ~5% of patients had strokes)

## 📈 Key Findings

### Correlation Analysis
- **Age** shows the strongest positive correlation with stroke occurrence
- **Hypertension** and **heart disease** are also positively correlated with stroke risk
- **Smoking status** shows weaker correlation than expected

### Interesting Observations
1. **Age Factor:** Older age groups (61-100 years) have significantly higher stroke incidence
2. **Medical History:** Patients with hypertension and heart disease show increased stroke risk
3. **Lifestyle:** 
   - Married individuals show higher stroke cases (likely due to age correlation)
   - Former smokers have slightly higher risk than current smokers
   - No significant difference between urban and rural residence

### Recommendations from Analysis
- Further investigation needed on why individuals with lower hypertension/heart disease have increased stroke risk
- Non-smokers showing higher stroke rates than smokers requires additional research
- BMI between 20-50 shows higher stroke probability
