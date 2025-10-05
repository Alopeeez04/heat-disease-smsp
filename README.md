# ❤️ Heart Disease Prediction
**Final Course Project – Statistical Models and Stochastic Processes**  
**Author:** Ainhoa López Carrasco  

---

## 🩺 Introduction

### What is Heart Disease?
Heart disease, also known as Cardiovascular Disease (CVD), refers to a group of heart conditions such as high blood pressure, stroke, and vascular dementia that negatively affect heart function and blood circulation. CVD remains the leading cause of global mortality, representing approximately **31% of all deaths worldwide** (~18 million per year).

The goal of this project is to identify **significant predictors** of heart disease mortality and construct an effective **predictive model** based on clinical and pathological information.

---

## ⚙️ Techniques

The statistical methods applied are:

- **Logistic Regression Analysis**
- **Maximum Likelihood Estimation (MLE)**
- **Likelihood Ratio Tests** (e.g., ANOVA)

Each patient in the dataset is labeled as:
- `1` → Died due to heart disease  
- `0` → Survived  

Logistic regression helps model the relationship between predictors and the likelihood of death, while MLE estimates model parameters by maximizing the likelihood function.

---

## 🧮 Dataset

The dataset was obtained from the [UC Irvine Machine Learning Repository](https://archive.ics.uci.edu/dataset/519/heart+failure+clinical+records) and contains **299 patients** with **13 clinical features**:

| Feature | Type | Description | Unit/Values |
|----------|------|-------------|--------------|
| Age | Integer | Age of the patient | Years |
| Anemia | Binary | Decrease of red blood cells or hemoglobin | 0 = False / 1 = True |
| Creatinine Phosphokinase | Integer | CPK enzyme level | mcg/L |
| Diabetes | Binary | Presence of diabetes | 0 = False / 1 = True |
| Ejection Fraction | Integer | % of blood leaving the heart per beat | % |
| High Blood Pressure | Binary | Hypertension | 0 = False / 1 = True |
| Platelets | Continuous | Platelet count in the blood | kilo platelets/mL |
| Serum Creatinine | Continuous | Level of serum creatinine | mg/dL |
| Serum Sodium | Integer | Level of serum sodium | mEq/L |
| Sex | Binary | Gender | 0 = Woman / 1 = Man |
| Smoking | Binary | Smoker status | 0 = False / 1 = True |
| Time | Integer | Follow-up period | Days |
| Death Event | Binary | Patient death | 0 = False / 1 = True |

---

## 📊 Data Analysis

Each predictor was analyzed individually through logistic regression and MLE, comparing p-values and confidence intervals (95%).

### 🔹 Significant Predictors
- **Age** → Significant (older patients have higher mortality)  
- **Ejection Fraction** → Significant (lower EF increases risk)  
- **Serum Creatinine** → Significant (higher levels increase mortality risk)

### 🔹 Non-Significant Predictors
Anemia, Diabetes, High Blood Pressure, Platelets, Serum Sodium (in the final model), Sex, and Smoking did not show significant correlation with mortality (p > 0.05).

---

## 🧠 Final Model

After iterative testing and removing non-significant predictors, the final model included:

- **Age**
- **Ejection Fraction**
- **Serum Creatinine**

The model achieved a **77% accuracy** in predicting patient outcomes.  
No multicollinearity was detected between predictors.

---

## 🧩 Conclusions

- Only 3 out of 11 predictors were statistically significant.  
- These variables (age, ejection fraction, and serum creatinine) are key indicators of mortality in heart disease patients.  
- The model correctly forecasts **77% of the cases**, indicating strong predictive potential.  
- Adding more clinical features could further improve accuracy and generalization.

---

## 📚 References

1. [Centers for Disease Control and Prevention – How the Heart Works](https://www.cdc.gov/ncbddd/spanish/heartdefects/howtheheartworks.html)  
2. [UCI Machine Learning Repository – Heart Failure Dataset](https://archive.ics.uci.edu/dataset/519/heart+failure+clinical+records)  
3. [British Heart Foundation – Cardiovascular Heart Disease](https://www.bhf.org.uk/informationsupport/conditions/cardiovascular-heart-disease)  
4. [NHLBI – Anemia](https://www.nhlbi.nih.gov/health/anemia)  
5. [Mount Sinai Health System – Creatine Phosphokinase Test](https://www.mountsinai.org/health-library/tests/creatine-phosphokinase-test)  
... *(Full bibliography as listed in the report)*

---

## 🧾 Acknowledgements

This project was developed as part of the **Statistical Models and Stochastic Processes** course, combining theory and data analysis in R to explore real-world clinical applications.
