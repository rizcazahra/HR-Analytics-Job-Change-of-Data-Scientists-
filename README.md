**HR Analytics: Job Change of Data Scientists**

**Background:**
A company in Big Data and Data Science aims to recruit data scientists from those who completed their courses. To optimize training costs and quality, the company wants to identify candidates genuinely interested in working for them post-training. Demographic, education, and experience data are available from candidate registrations.

**Dataset:** [HR Analytics: Job Change of Data Scientists](https://www.kaggle.com/datasets/arashnic/hr-analytics-job-change-of-data-scientists)

**Inspirations:**
- Predicting a candidate's probability of working for the company.
- Interpreting the model to understand influential features in candidate decisions.

**Table of Contents:**
**Stage 1: EDA, Insights, and Visualization**
- Data Exploration
  - Observations:
    - 19,158 rows, mostly categorical.
    - Highest missing values in company_type, company_size, gender, and major_discipline.
    - Some columns with null values (Non-Null Count < total rows).
    - Notable columns for follow-up: experience, company_size, last_new_job.
    - No missing values in numeric data.
  - Business Insights:
    - City Development Index (CDI) correlates with job-seeking tendencies.
    - Training hours impact job-seeking; longer hours, less likelihood.
    - Gender, company type, education level, major discipline, and experience influence job-seeking.
    - Last New Job shows a correlation with job-seeking intentions.

**Stage 2: Data Preprocessing**
- Data Cleansing:
  - Handle Missing Values: MICE Iterative Imputer.
  - Handle Duplicates: Removed 49 duplicate rows.
  - Handle Outliers: Visualized data, Z-Score, and IQR Method.
  - Feature Transformation: Log transformation, standardization, and normalization.
  - Feature Encoding: Label Encoding and One-Hot Encoding.
  - Handle Class Imbalance: Used SMOTE and SVM SMOTE techniques.
- Feature Engineering:
  - Feature Selection: Removed enrollee_id.
  - Feature Extraction: Simplified experience and company size.
  - Additional Features: Candidate background (Age, Marital status, Dependents, Previous Salary, Salary Increase, Average Working Hours, GPA), Training Score.

**Stage 3: Machine Learning Modeling and Evaluation**
- Modeling:
  - Base Model:
    ![image](https://user-images.githubusercontent.com/84758353/180401623-74442e41-0269-4de0-9c0f-f51c6da24563.png)

- Feature Importance:
  ![image](https://user-images.githubusercontent.com/84758353/180401902-3b9bc045-8d7d-4e52-b635-3c3c26cbcb5a.png)
- Recommendations:
  ![image](https://user-images.githubusercontent.com/84758353/180402287-c5d737e7-7c4d-4612-9509-a984d483b3c9.png)

*Summary:*
This project focuses on predicting data scientist job change decisions post-training. It involves comprehensive stages such as data exploration, preprocessing, machine learning modeling, and feature interpretation. Key insights from exploratory data analysis (EDA) and business insights guide the preprocessing steps. The modeling phase includes a base model and hyperparameter tuning. Feature importance analysis helps identify crucial factors influencing job change decisions. The project concludes with recommendations, though specific details are not provided in the summary.
