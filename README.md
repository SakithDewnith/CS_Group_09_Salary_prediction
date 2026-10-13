# Employee Salary Analysis & Prediction 

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

## Skills:

**Programming & Libraries:** Python, Pandas, NumPy, Scikit-learn

**Data Preparation:** Data Cleaning, Feature Engineering (Encoding, Scaling)

**Analysis & Visualization:** Exploratory Data Analysis (EDA), Statistical Analysis, Matplotlib, Seaborn, Insight Reporting

**Machine Learning & Evaluation:** Linear Regression, Cross-Validation, Model Evaluation (R², RMSE)
<br>
<br>

## Methodology

The project uses an employee salary dataset containing 6,704 records and six features: Age, Gender, Education Level, Job Title, Years of Experience, and Salary.

**Overall Project Methodology**

The group project followed a structured workflow involving data cleaning, exploratory data analysis, feature preprocessing, regression model development, performance evaluation, and model comparison to investigate approaches to assess their suitability for employee salary prediction.

<br>

**My Contribution: Linear Regression**

I independently developed and evaluated a Linear Regression pipeline using the employee salary dataset.

| Stage                                      | Technical Implementation                                                                                                                                                                                                                                                                                                                                                                      |
| ------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **1. Data Inspection & Cleaning**          | Inspected data types, missing values, duplicate records, inconsistent labels and numerical distributions and Removed missing values, standardized inconsistent education labels, removed duplicate records, filtered salaries at or below 1,000 and above the IQR-based upper bound check to exclude unusually high salary values.                                                                                                                                         |
| **2. Exploratory Data Analysis (EDA)**     | Used Pandas, Seaborn, and Matplotlib to analyse salary, age, and experience distributions; compare salaries across education levels, job titles, and gender; and investigate numerical relationships using scatter plots, correlation analysis, and pair plots.                                                                                                                               |
| **3. Feature Preparation & Preprocessing** | Separated `Salary` as the target variable. Applied an 80/20 train-test split with `random_state=42`. Grouped infrequent job titles and education categories with fewer than 10 training records into `Other`, applied `OneHotEncoder` to categorical features and `StandardScaler` to numerical features, and combined preprocessing and Linear Regression in a Scikit-learn pipeline to keep the transformations and model organized.|
| **4. Model Training & Validation**         | Trained a Scikit-learn `LinearRegression` model and performed five-fold cross-validation on the training set using R² as the scoring metric.                                                                                                                                                                                                                                                  |
| **5. Model Evaluation & Interpretation**   | Evaluated test-set performance using R² and RMSE. Analysed actual and predicted salaries using a scatter plot, examined residual plots and the residual distribution to assess prediction errors. Visualized model coefficients to explore how the encoded features and numerical inputs contributed to the model's predictions.                                                                                                                                                                                       |
| **6. Salary Prediction & Model Export**    | Generated a salary estimate for a sample employee profile and saved the fitted preprocessing and regression pipeline as a `.pkl` file using Joblib for potential reuse.                                                                                                                                                                                                             |
<br>

## Results & Key Insights

* **Data Quality:**  The original dataset contained 6,704 rows, including 4,912 duplicate records. After cleaning, 1,782 records remained for analysis.

* **Key Salary Relationships:** Years of Experience (\(r = 0.82\)) and Age (\(r = 0.77\)) showed strong positive correlations with Salary. Age and Experience were also highly correlated (\(r = 0.94\)). This suggests that employees with more experience and older employees generally tended to earn higher salaries in this dataset, while the overlap between Age and Experience makes their individual effects harder to distinguish.

* **Salary Patterns:** Exploratory analysis and model coefficients showed differences in predicted salaries across education levels and job titles. Senior and managerial roles were generally associated with higher predicted salaries, suggesting that both qualifications and job seniority are relevant to salary estimation.

* **Model Performance:** The Linear Regression pipeline achieved a **test R² of 0.806**, a **five-fold cross-validation R² of 0.819**, and a **test RMSE of approximately 22,598 salary units**. The test R² indicates that the model explained about 80.6% of the salary variation in the test set. The similar scores suggest no obvious signs of substantial overfitting.

* **Group Model Comparison:** The group compared Random Forest, Decision Tree, XGBoost, K-Nearest Neighbors (KNN), Linear Regression, and Lasso Regression. Random Forest had the strongest reported results, with a test R² of 0.98 and an RMSE of 6,849, indicating better reported predictive performance than the other models.

* **Model Limitations:** Residual analysis indicated larger prediction errors at higher predicted salary levels in in my Linear Regression . The strong correlation between Age and Experience also makes their individual regression coefficients harder to interpret. Gender was explored during data analysis but was not included as a model input.

* **Example Prediction:** For a sample 30-year-old Data Analyst with a Bachelor's degree and five years of experience, the model predicted approximately **114,006 salary units**. This demonstrates how the trained model can estimate salary for a given employee profile, although the prediction is an estimate rather than a guaranteed salary.
<br>

## Future Improvements

* **Feature Engineering:** Explore additional features and transformations to improve salary predictions.
* **Model Optimization:** Apply hyperparameter tuning to improve model performance and stability.
* **Ensemble Methods:** Experiment with combining strong models, such as Random Forest and XGBoost, where appropriate.
* **More Reliable Data:** Collect a larger, more representative dataset and validate duplicate records to improve generalization.
* **Alternative Algorithms:** Explore LightGBM and CatBoost and compare their performance against existing models using consistent evaluation procedures.
* **Model Validation:** Evaluate the selected model on independent data to assess its performance on unseen employee records.
<br>

## Business Recommendations

* **Compensation Planning:** Use predicted salaries as a reference when estimating salary ranges based on job title, experience, and education.
* **Salary Benchmarking:** Compare model estimates with market salary data and internal compensation policies before making pay decisions.
* **Human Review:** Treat predictions as decision-support estimates rather than final salary recommendations, and validate their accuracy and fairness before practical use.
