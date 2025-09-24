# **Lead Scoring Model for X Education**
# 1. Objective
The objective of this project is to develop a robust machine learning model for **X Education** that can accurately predict the probability of a lead converting into a paying customer.  
The model is designed to generate a **lead score between 0 and 100** for each lead, enabling the sales team to prioritize their efforts on the most promising "hot" leads.  
This strategic focus is aimed at significantly improving the lead conversion rate, which is currently around **30%**.

---

# 2. Problem Statement
X Education faces a challenge of **low lead conversion** despite a high volume of leads.  
The existing process of calling and emailing every lead is inefficient.  
By building a predictive model, we can identify leads with a high potential for conversion, allowing the sales team to optimize their time and resources.  
The ultimate goal is to **increase the lead conversion rate** by focusing on leads with a higher lead score.

---

# 3. Dataset
The project utilizes a dataset obtained from **Kaggle**.  
This dataset contains information on leads, including their online activity, demographic details, and communication history.

- **Total Records:** 9,240  
- **Total Features:** 37  
- **Target Variable:** `Converted` (1 for converted, 0 for not converted)  
- **Key Features:**  
  - Lead Origin  
  - Lead Source  
  - TotalVisits  
  - Total Time Spent on Website  
  - Page Views Per Visit  
  - Last Activity  
  - Specialization  
  - What is your current occupation  
  - City  
  - Last Notable Activity  

---

# 4. Project Stages & Methodology

## Stage 1: Initial Data Exploration
- **Initial Inspection:** Conducted an initial analysis of the dataset to understand its structure, identify data types, and check for missing values and duplicates.  
- **Summary Statistics:** Generated descriptive statistics for numerical columns to identify data distribution and potential outliers.

## Stage 2: Data Cleaning and Preprocessing
- **Missing Value Handling:**  
  - Dropped columns with over 40% missing data.  
  - Imputed missing values in categorical columns with the mode.  
  - Imputed missing values in numerical columns with the median.  
- **Feature Removal:** Removed irrelevant and redundant columns that would not contribute to the model's predictive power (e.g., Prospect ID, Lead Number, Country, and other single-value columns).  
- **Outlier Treatment:** Applied the Interquartile Range (IQR) method to remove outliers from numerical features like *TotalVisits* and *Page Views Per Visit*.  
- **Duplicate Removal:** Dropped 1,823 duplicate rows that appeared after data cleaning.  
- **Final Dataset:** 6,822 rows and 13 columns.

## Stage 3: Exploratory Data Analysis (EDA)
- **Website Behavior:**  
  - A moderate positive correlation (**r = 0.42**) was found between *Total Time Spent on Website* and the `Converted` target variable, indicating that time spent on the site is a strong predictor of conversion.  
  - *TotalVisits* and *Page Views Per Visit* showed a weak correlation with conversion.  
- **Lead Demographics:** Insights were gained into the most effective lead sources (Google, Direct Traffic), origins (Landing Page Submission, API), and high-converting specializations (Healthcare Management).  
- **City Analysis:** Mumbai was identified as the city with the highest lead volume and conversion rate.

## Stage 4: Model Building and Evaluation

- **Data Preparation:**  
  - The cleaned data was split into training and testing sets.  
  - Categorical features were converted using **One-Hot Encoding**.
  - Feature Selection by **Recursive Feature Elimination with Cross Validation** (RFECV) to get the Optimal Feature. 
  - Numerical features were scaled using **StandardScaler**.
    
- **Model Selection:** Multiple classification algorithms were planned for evaluation to find the best-performing model:  
  - Logistic Regression  
  - Random Forest Classifier  
  - Decision Tree Classifier  
  - Support Vector Machine (SVM)  
  - K-Nearest Neighbor (KNN)  
  - XGBoost Classifier
    
- **Evaluation Metrics:** The models will be evaluated using key metrics such as **Precision**, **Recall**, **F1-Score**, and the **ROC-AUC** curve.  
  The goal is to maximize the recall and precision to effectively identify potential hot leads.
