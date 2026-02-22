# Heart_Disease_Dataset_Analysis
Analisys on dataset of patients with heart disease. In this work I testing hypothesis and finding which features more impact on risk score of getting heart disease

## 1. Data Understanding & Integrity

This dataset is perfect. There is no missing values, duplicates and imposible values. 5500 rows and 17 columns in dataset. Here is the attributes description.

**Attributes Description:**

| Attribute                            | Type                 | Description                                                                               |
| ------------------------------------ | -------------------- | ----------------------------------------------------------------------------------------- |
| **Patient_ID**                       | Integer / String     | Unique identifier assigned to each patient; used only for record identification.          |
| **age**                              | Integer              | Age of the patient in years; higher age is associated with increased cardiovascular risk. |
| **bmi**                              | Float                | Body Mass Index; indicator of body fat based on height and weight.                        |
| **systolic_bp**                      | Integer              | Systolic blood pressure (mmHg); pressure during heart contraction.                        |
| **diastolic_bp**                     | Integer              | Diastolic blood pressure (mmHg); pressure between heartbeats.                             |
| **cholesterol_mg_dl**                | Integer              | Total cholesterol level in mg/dL; elevated levels increase heart disease risk.            |
| **resting_heart_rate**               | Integer              | Resting heart rate in beats per minute.                                                   |
| **smoking_status**                   | Categorical (String) | Smoking behavior category: *Never*, *Former*, or *Current*.                               |
| **daily_steps**                      | Integer              | Average number of steps taken per day; reflects daily activity level.                     |
| **stress_level**                     | Integer (1–10)       | Self-reported stress level on a scale from 1 (low) to 10 (high).                          |
| **physical_activity_hours_per_week** | Float                | Total weekly hours of structured physical exercise.                                       |
| **sleep_hours**                      | Float                | Average number of hours slept per night.                                                  |
| **family_history_heart_disease**     | Binary/Categorical              | Indicates presence (`True`) or absence (`False`) of family history of heart disease.      |
| **diet_quality_score**               | Integer (1–10)       | Score representing overall diet quality; higher values indicate healthier diet.           |
| **alcohol_units_per_week**           | Float                | Average number of alcohol units consumed per week.                                        |
| **heart_disease_risk_score(target)**         | Float (0–100)        | Calculated cardiovascular risk score summarizing multiple risk factors.                   |
| **risk_category**                    | Categorical (String) | Risk classification label: *Low*, *Medium*, or *High*.                                    |

## 2. Descriptive Statistics & Distributions

**Numerical columns:** 'Patient_ID', 'age', 'bmi', 'systolic_bp', 'diastolic_bp',
       'cholesterol_mg_dl', 'resting_heart_rate', 'daily_steps',
       'stress_level', 'physical_activity_hours_per_week', 'sleep_hours',
       'diet_quality_score', 'alcohol_units_per_week',
       'heart_disease_risk_score'.

**Categorical columns:** 'smoking_status', 'family_history_heart_disease', 'risk_category'

**Distribution of Age**

<img width="571" height="455" alt="image" src="https://github.com/user-attachments/assets/b83add5a-051e-426f-ba4d-80c14846dfd1" />

**Physical Activity Hours Per Week**

<img width="571" height="455" alt="image" src="https://github.com/user-attachments/assets/a88ff0cb-8da0-476f-afe7-557fb838045d" />

**Smoking Status**

<img width="580" height="488" alt="image" src="https://github.com/user-attachments/assets/c77b65b5-5333-4174-874a-69f7ddb0e57c" />

**Risk Category Distribution**

<img width="389" height="411" alt="image" src="https://github.com/user-attachments/assets/036a24e7-596d-4245-8098-d0d924704feb" />

**Sleep Hours Boxplot**

<img width="543" height="435" alt="image" src="https://github.com/user-attachments/assets/1b77fe65-0363-445b-8559-2285feb7ca34" />

**Distribution of BMI**

This column is approximately normal

<img width="556" height="435" alt="image" src="https://github.com/user-attachments/assets/65f496bf-c5d5-4e68-9fc0-0ba70ae7a34a" />

**Distribution of Heart Resting Rate(bpm)**

This plot almost follows a normal distribution

<img width="556" height="435" alt="image" src="https://github.com/user-attachments/assets/b006a98b-f6d2-47c9-99b9-8ade281974be" />


**Overall, we can see visualization of significant characteristics, also we ensured that some columns follows normal distribution.**

## 3. Parameter Estimation & Confidence Intervals

I take **'Age'** column for observation. 

Point estimate of the population mean age: 53.87 years

* 95% Confidence Interval for Population Mean Age: (53.31, 54.43) years

* 99% Confidence Interval for Population Mean Age: (53.14, 54.61) years

* 90% Confidence Interval for Population Mean Age: (53.40, 54.34) years

A higher confidence level (e.g., 99%) would result in a wider confidence interval, as we need to be more certain to capture the true population parameter. Conversely, a lower confidence level (e.g., 90%) would result in a narrower interval but with less certainty.

A larger sample size generally leads to a smaller standard error and thus a narrower confidence interval (assuming the same confidence level). This is because a larger sample provides more information about the population, leading to a more precise estimate.

## 4. Hypothesis Testing & Statistical Errors

I tested several hypothesis using suitable method like sample t-test, chi-square test of independence, ANOVA Test.

### 1. Independent Samples t-test, Welch's t-test

**Hypothesis Test:** Comparing Heart Disease Risk Score based on Family History

**Null Hypothesis (H0):** There is no significant difference in the mean heart_disease_risk_score between patients with and without a family history of heart disease.

**Alternative Hypothesis (H1):** There is a significant difference in the mean heart_disease_risk_score between patients with and without a family history of heart disease.

---

**Significance Level (α):** 0.05

**Test Statistic (t):** 11.8734

**P-value:** 0.0000...

**Conclusion:** Reject the null hypothesis.

**Discussion of Effect Size:**

Mean heart disease risk score for patients with family history: 44.31

Mean heart disease risk score for patients without family history: 35.30

**Cohen's d (Effect Size):** 0.376

### 2. Chi-square Test of Independence

**Hypotheses test:** Analyze the relationship between 'smoking_status' and 'risk_category'

**Null Hypothesis (H0):** smoking_status and risk_category are independent. There is no association between a person's smoking status and their heart disease risk category.

**Alternative Hypothesis (H1):** smoking_status and risk_category are not independent. There is a significant association between a person's smoking status and their heart disease risk category.

---

**Chi-square Statistic:** 839.98

**P-value:** 0.000...

**Degrees of Freedom:** 4

The p-value is far below the 0.05 threshold. Reject the null hypothesis.

There is a statistically significant association between smoking status and heart disease risk category.

**Cramér's V: 0.276**

0.276 ≈ small-to-moderate effect

Smoking status explains a meaningful but not overwhelming portion of variability in risk category.

