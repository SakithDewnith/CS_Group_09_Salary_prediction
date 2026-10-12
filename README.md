# Employee Salary Prediction & Analysis

## Executive Summary

In many organizations, employee salaries vary based on factors such as professional experience, education level, and job role. This project aims to develop regression-based machine learning models to predict employee salaries using these characteristics. The analysis explores salary patterns and compares model performance to identify suitable approaches for salary estimation. The findings may support HR departments in compensation planning and data-informed decision-making.


<br>

**Workflow:**
<p align="center">
<img width="624" height="100" alt="Employee_salary_prediction_proje…_20261012152400" src="https://github.com/user-attachments/assets/5f0af719-0cc6-48d3-b399-13bc18435833" />
</p>

<br> 

## Business Problem:
Employee compensation is a significant business cost, making accurate salary estimation important for compensation planning and budget allocation. However, differences in job roles, education, and professional experience make it challenging to determine appropriate salary levels consistently. The business needs a data-driven approach to analyse salary patterns, understand the factors influencing compensation, and develop reliable salary predictions to support informed business decisions. 
<br>
<br>

## Methodology

The project uses an employee salary dataset containing 6,704 records and six features: Age, Gender, Education Level, Job Title, Years of Experience, and Salary.

**Overall Project Methodology**

The project followed a structured workflow involving data cleaning, exploratory data analysis, feature preprocessing, regression model development, performance evaluation, and model comparison. Multiple modelling approaches were explored to assess their suitability for employee salary prediction.
<br>

**My Contribution: Linear Regression**

I independently developed and evaluated a Linear Regression pipeline using the employee salary dataset.

**1. Data Cleaning**

* Examined missing values and duplicate records.
* Standardized inconsistent education-level labels.
* Filtered records with missing values and salary values identified as outliers.

**2. Exploratory Data Analysis**

* Analysed salary distributions and relationships with age, education, job titles, and professional experience.
* Used statistical summaries and visualizations to explore salary patterns.

**3. Feature Preprocessing**

* Applied one-hot encoding to categorical features, including Job Title and Education Level.
* Standardized numerical features, including Age and Years of Experience.
* Grouped infrequent job titles and education categories into an "Other" category.

**4. Model Development**

* Built a Linear Regression pipeline using an 80/20 train-test split.
* Used a fixed random state of 42 to support reproducibility.

**5. Model Evaluation**

* Evaluated the model using test-set R², RMSE, and five-fold cross-validation.
* Examined actual-versus-predicted values and residual plots to assess prediction errors.
