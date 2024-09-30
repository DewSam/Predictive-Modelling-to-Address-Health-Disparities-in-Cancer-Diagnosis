# Predictive-Modelling-to-Address-Health-Disparities-in-Cancer-Diagnosis

# Predicting Metastatic Cancer Diagnosis: Big Data Approach

## 1. Introduction
Health disparities in cancer diagnosis and treatment are critical public health challenges. This project leverages **Big Data analytics** to explore inequities in healthcare, particularly in the diagnosis timing of metastatic cancer. The goal is to understand how **demographic and environmental factors** influence medical outcomes and to develop **predictive models** using **PySpark** that can effectively address these disparities.

## 2. Project Objectives
- **Primary Objective:** Develop a **predictive model** capable of forecasting if patients will receive a diagnosis of **metastatic triple-negative breast cancer** within 90 days. Early detection is vital for effective intervention.
- **Secondary Objectives:**
  - **Feature Identification:** Identify key features contributing to diagnosis delays.
  - **Impact of Demographics & Environment:** Understand how demographic and environmental factors influence diagnosis timing.
  - **Insurance Analysis:** Explore how different types of insurance affect diagnostic timelines.

## 3. Data Description
The dataset includes **12,906 patient records** from 2015 to 2018, each diagnosed with metastatic cancer. Features include:
- **Patient Demographics:** Age, gender, race, and state.
- **Health Data:** Breast and metastatic cancer diagnosis codes.
- **Socioeconomic Data:** Income, education levels, employment status (by zip code).
- **Environmental Data:** Levels of **pollutants** (e.g., O3, PM2.5, NO2).

## 4. Methodology
- **Data Ingestion & Cleaning:** Performed using **PySpark**. Data cleaning involved imputation, feature engineering, and transformation.
- **Model Training:** Multiple models were trained, including **Random Forest**, **Gradient Boost Classifier**, **Decision Tree**, and **Logistic Regression**.
- **Model Validation:** The models were validated using **AUC (Area Under the Curve)** to measure performance.

## 5. Exploratory Data Analysis (EDA)
### Age & BMI Distribution
- Age and BMI distributions did not significantly differ between early and late diagnoses, suggesting minimal impact on diagnosis timing.

### Socioeconomic Factors
- Lower socioeconomic status (income, education) appears correlated with delayed diagnoses, suggesting barriers to healthcare access.

### Insurance Analysis
- No significant differences were found between diagnosis timings across different insurance types (Medicare, Medicaid, commercial).

### Environmental Factors
- High pollutant areas showed slight trends towards later diagnoses, though the overall correlation was weak.

### Demographic Influences
- States with the highest late diagnoses: **Kentucky, Virginia, New Mexico, New York, Illinois**.
- Transition to **ICD-10** coding led to improved diagnostic accuracy and timeliness.

## 6. Pre-Modelling (Data Preprocessing)
Steps included:
- Dropping columns with >90% missing values.
- Mode/median imputation for categorical and numerical features.
- Two new features: **ICD version** and **metastatic diagnosis category**.

## 7. Modelling and Results
### Baseline Models
- **Random Forest**: Best-performing model with **AUC of 81.35%**.
- Feature selection improved AUC scores for all models by ~1%.

### Commercial Plan Model Results
- **Random Forest** performed best with **AUC of 74.48%**, but overall performance was lower than the general model, suggesting that insurance type has limited predictive value.

## 8. Discussion of Findings
- **ICD-10** coding is a strong predictor of early diagnoses, especially among younger patients.
- **Education** and **socioeconomic factors** play crucial roles in diagnostic timing, while environmental factors and insurance types had a weaker influence.

## 9. Challenges and Limitations
- **Missing data** in BMI and payer types.
- **PySpark limitations** in handling more detailed analyses.
  
## 10. Conclusion
This project highlights the potential of **Big Data and predictive analytics** in addressing healthcare inequities. By understanding key factors that delay cancer diagnosis, we can inform policies to reduce disparities and improve early detection.

### Future Recommendations:
- Targeted screening programs for high-risk demographics.
- Further research on ICD-10's impact on other healthcare areas.
- Address age-based disparities in diagnostic practices.

## 11. References & Acknowledgments
- **PySpark Documentation:** [https://spark.apache.org/docs/latest/api/python/reference/index.html](https://spark.apache.org/docs/latest/api/python/reference/index.html)
- **Healthcare Datasets & Coding Systems:** 
  - [WiDS Datathon 2024 Dataset](https://www.kaggle.com/competitions/widsdatathon2024-challenge1/data)
  - [ICD10 Chart Builder](http://www.icd10charts.com/chartbuilder.php?chart=555f9168e5)

Contributions from all team members and project advisors are gratefully acknowledged.
