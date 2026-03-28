# Student Dropout Prediction Dataset

# Overview
This dataset simulates a real-world scenario where a university aims to predict student dropout during the first academic year. Designed for Supervised Learning (Classification), the target variable is Dropout (Yes/No). It can be used with models like Logistic Regression, Decision Trees, or Random Forest to estimate dropout risk based on various factors.

# Dataset Description
The dataset contains 500 records with demographic, academic, and financial information. It includes features like age, gender, and origin, alongside academic data such as high school average, admission score, and first-semester performance. It also incorporates financial details like socioeconomic level, scholarships, and active loans.

### Features
| Variable             | Type       | Description              | Range/Categories                      |
| -------------------- | ---------- | ------------------------ | ------------------------------------- |
| Student_ID           | Integer     | Unique identifier        | 1 to 500                              |
| Age                  | Integer     | Student's age            | 17 to 30 (with outliers)              |
| Gender               | Categorical | Gender                   | Male, Female, Non-Binary              |
| Place_of_Origin      | Categorical | Origin                   | Urban, Rural, Suburban, International |
| HS_Grade_Avg         | Float       | High school average      | 50.0 to 100.0 (with outliers)         |
| Admission_Test_Score | Float       | Admission exam score     | 0.0 to 100.0                          |
| First_Semester_Grade | Float       | 1st semester average     | 0.0 to 100.0 (with nulls)             |
| Socioeconomic_Level  | Categorical | Socioeconomic strata     | Low, Middle, High                     |
| Scholarship          | Categorical | Scholarship status       | Yes, No                               |
| Financial_Loan       | Categorical | Active financial loan    | Yes, No (with nulls)                  |
| Dropout              | Categorical | Target variable          | Yes, No                               |

## Data Generation
Synthetically generated using numpy and pandas. To simulate realistic behavior, a risk-based logic was implemented: dropout probability increases with poor academic performance (especially in the first semester), low socioeconomic status without scholarships, rural origins, low admission scores, and active financial loans. Random noise was added to prevent perfectly separable classes and mimic real-world unpredictability.

## Noise Injection
To enhance realism, null values and outliers were intentionally included:

- Nulls: ~5% of First_Semester_Grade and ~2.5% of Financial_Loan values were replaced with NaN.
- Outliers: Unrealistic high school averages (150-200) and out-of-bounds ages (5, 12, 65) were added to simulate registry errors or extremely rare cases.

## Usage Notes
Due to the presence of nulls, categorical variables, and outliers, preprocessing is required before training machine learning models. This includes missing data imputation, categorical encoding, and feature scaling. This dataset is tailored for classification tasks, allowing you to evaluate various models in a controlled yet realistic environment.
