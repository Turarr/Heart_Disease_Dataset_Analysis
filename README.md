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

**Conclusion:** Reject the null hypothesis. The difference is definitely there, but it is considered small. Family history matters, but it isn't the only thing driving the risk score.

**Errors**

**False Positive (Type I):** Claiming family history matters when it actually doesn’t. You’ve set the risk of this happening at 5%.

**False Negative (Type II):** Missing the connection entirely and saying there’s no difference when there actually is.

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

### 3. ANOVA testing

**Hypotheses test:** Analyze the relationship between 'Age' and 'Risk Category'. Does every risk category have different age groups?

**Null Hypothesis (H0):** The mean age is the same across all heart disease risk categories.

**Alternative Hypothesis (H1):** At least one risk category has a mean age that is different from the others.

**Every risk categories mean age:**
* Low: 37.0
* Medium: 55.5
* High: 73.0

<img width="1489" height="490" alt="image" src="https://github.com/user-attachments/assets/800030ea-179c-495b-9225-25750ece251c" />

**One-way ANOVA results**

**ANOVA F-statistic:** 2030.91

**ANOVA P-value:** 0.000e+00

**Effect Size:**

**Eta-squared (η²):** 0.425

**Post-hoc analysis (Tukey HSD)**

| Group 1 | Group 2 | Mean Difference | p-value (adj) | Lower CI | Upper CI | Significant? |
| ------- | ------- | --------------- | ------------- | -------- | -------- | ------------ |
| High    | Low     | -36.0351        | 0.0000        | -37.3672 | -34.7030 | ✅ Yes        |
| High    | Medium  | -17.5450        | 0.0000        | -18.8236 | -16.2664 | ✅ Yes        |
| Low     | Medium  | 18.4901         | 0.0000        | 17.3044  | 19.6758  | ✅ Yes        |


<img width="860" height="547" alt="image" src="https://github.com/user-attachments/assets/61917ee3-189c-4959-8a4d-63dd5f5b2e88" />

**Conclusion:**

A one-way ANOVA revealed a statistically significant effect of risk category on age, with large effect size. Post-hoc Tukey tests indicated that all three risk groups differed significantly from each other, showing a clear monotonic increase in age from low- to high-risk categories. These findings confirm age as a major contributor to cardiovascular risk stratification.

## Regression or Generalized Linear Model

The variables bmi, age, systolic blood pressure, family history of heart disease used as predictors. These are justified because medical science shows they directly impact heart health. As target we predict the **heart disease risk score**.

**R²** = 0.929

The model explains 92.9% of the variability in heart disease risk scores.
In medical and public health research, this is an exceptionally strong model fit. It indicates that the included predictors (age, BMI, blood pressure, family history, lifestyle factors) collectively capture most of the variation in risk.

**Prob (F-statistic)** = 0.00

The overall model is highly statistically significant (p < 0.001).
This means that, taken together, the predictors provide meaningful explanatory power and the model is not due to random chance.

**Interpretation of Individual Predictors**

| Variable                             | Coefficient | Direction     | Interpretation                                                                                                                            | Statistical Significance |
| ------------------------------------ | ----------- | ------------- | ----------------------------------------------------------------------------------------------------------------------------------------- | ------------------------ |
| **family_history_int**               | +9.5351     | ⬆ Risk        | Having a family history of heart disease increases the predicted risk score by **9.54 points** — the strongest overall predictor.         | Significant              |
| **systolic_bp (mmHg)**               | +0.8046     | ⬆ Risk        | Each 1 mmHg increase in systolic BP increases risk by **0.80 points**. Strongest clinical continuous predictor.                           | Significant              |
| **stress_level**                     | +0.4755     | ⬆ Risk        | Each 1-point increase in stress raises risk by **0.48 points**.                                                                           | Significant              |
| **bmi**                              | +0.3915     | ⬆ Risk        | Each 1-unit increase in BMI increases risk by **0.39 points**.                                                                            | Significant              |
| **age (years)**                      | +0.3075     | ⬆ Risk        | Each additional year of age increases risk by **0.31 points**.                                                                            | Significant              |
| **cholesterol_mg_dl**                | +0.1230     | ⬆ Risk        | Each 1 mg/dL increase in cholesterol raises risk by **0.12 points** (100 mg/dL → +12 points).                                             | Significant              |
| **physical_activity_hours_per_week** | −1.3090     | ⬇ Risk        | Each additional hour of weekly exercise reduces risk by **1.31 points** — strongest protective factor.                                    | Significant              |
| **diet_quality_score**               | −1.1209     | ⬇ Risk        | Each 1-point improvement in diet quality lowers risk by **1.12 points**.                                                                  | Significant              |
| **alcohol_units_per_week**           | +0.0352     | ⬆ Risk (weak) | Small positive effect, but **not statistically significant (p = 0.216)**. Cannot confidently conclude alcohol impacts risk in this model. | Not Significant          |

**Metrics:**

**MAE (6.08):** On average, your model's predictions are off by about 6 points. Given that your risk scores go up to 100, a 6% average error is quite low.

**MSE (56.96):** This penalizes larger errors more heavily. Since this number isn't massive compared to the MAE, it suggests you don't have too many "extreme" outliers where the model was catastrophically wrong.

<img width="1034" height="490" alt="image" src="https://github.com/user-attachments/assets/5c0097a1-0733-4f45-84d5-faef8ce95158" />
