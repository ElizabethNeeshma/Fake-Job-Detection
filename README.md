# **Fake Job Posting Detection Using Machine Learning**

This project aims to detect fake job postings using machine learning models trained on text and metadata from the Kaggle Fake Job Postings Dataset.
The goal is to help online job platforms automatically flag suspicious job ads and protect job seekers.

## **🔍 Project Overview**

Problem: Online job scams are increasing, and manual moderation cannot scale.<br>
Goal: Build a machine learning model that can classify job postings as real or fake.<br>
Approach: Use text features (TF-IDF), metadata, and ML models to identify fraud patterns.<br>

## **📂 Dataset**

Source: Kaggle — Fake Job Posting Dataset
Link: https://www.kaggle.com/datasets/shivamb/real-or-fake-fake-jobposting-prediction

The dataset contains 18,000 job postings, where only a small portion are fake.
Columns include:

title, company_profile, description, requirements, benefits

employment_type, required_experience, required_education


 ## **⚙️Methodology**
### **1. Data Cleaning**

- Filled missing values

- Combined all text fields into one description

- Converted text to lowercase and removed URLs, numbers, and punctuation

### **2. Feature Engineering**

- Used TF-IDF (unigrams and bigrams, 5,000 features)

- Created numeric features (word count, sentence count, URL presence)

- Applied One-Hot Encoding for categorical fields

### **3. Model Training**

- Trained four machine learning models:

- Logistic Regression (with balanced class weights)

- Random Forest (300 trees)

- SVM (Calibrated)

- XGBoost (best performance)

### **4. Evaluation Metrics**

- Accuracy

- Precision

- Recall

- F1-score for the fake class (most important)

- ROC Curve and AUC

## **🏆 Results**
## **Model Performance**

| Model               | Accuracy | F1 (Fake Class) |
|---------------------|----------|-----------------|
| XGBoost             | **0.98** | **0.83**        |
| SVM                 | 0.98     | 0.82            |
| Logistic Regression | 0.97     | 0.73            |
| Random Forest       | 0.97     | 0.70            |


XGBoost gave the best overall performance, especially for detecting fake posts.

## **🔧 Test Run Example**

Input:
“We are hiring immediately! Click the link below to apply…”

Model Output:
FAKE (0.87 probability)

## **🚀 Future Improvements**

- Use transformer models like BERT for better text understanding

- Try imbalance methods such as SMOTE or focal loss

- Add more features like company reputation or IP/geolocation

- Deploy the model as an API for real-time screening
