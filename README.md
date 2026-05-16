# BRFSS Diabetes Risk Prediction — StFX 2025

A machine learning study for predicting diabetes risk using the 
Behavioral Risk Factor Surveillance System (BRFSS) population 
health survey dataset. Developed as part of **CSCI 546** at 
St. Francis Xavier University.

---

## 👩‍🎓 Authors

**Gayathri Thirumoorthi** | x2024gpp@stfx.ca  
**Pradeep Reddy Lopinti** | x2024gqa@stfx.ca  
**Daniel Attah** | x2025ckz@stfx.ca  

Department of Computer Science, St. Francis Xavier University, 
Nova Scotia, Canada

---

## 📄 Project Overview

Diabetes mellitus is one of the most significant global public 
health challenges. This study investigates the use of machine 
learning techniques to predict diabetes risk from large-scale 
survey data, integrating data preprocessing, class imbalance 
analysis, feature selection, and explainable AI.

**Primary Dataset:** BRFSS 2019 (~80,000 records)  
**Secondary Dataset:** BRFSS 2020 (~400,000 records)  
**Target Variable:** DIABETE4 (binary — diabetic / non-diabetic)  
**Framework:** df-analyze (automated ML pipeline)

---

## 🔬 Methodology

### Data Preprocessing
- Removal of incomplete/duplicate records
- Missing value handling via deletion or imputation
- Categorical variable encoding
- Normalization and scaling of continuous variables

### Feature Groups (Hypotheses)
| Run | Feature Group | Hypothesis |
|---|---|---|
| run1_full | All features | Full dataset produces highest performance |
| run2_demographics | Age, sex, sociodemographic | Demographics alone have limited signal |
| run3_lifestyle | Smoking, activity, alcohol | Lifestyle provides moderate signal |
| run4_general_health | BP, cholesterol, BMI | General health provides strongest signal |
| run5_female_only | Female subgroup only | Gender-specific patterns affect prediction |

### Models Evaluated
`CatBoost` `LightGBM` `Random Forest` `GANDALF` 
`Logistic Regression` `K-Nearest Neighbors` `Dummy Baseline`

### Feature Selection Methods
- Association-based selection
- Prediction-based selection
- Embedded linear selection
- Wrapper-based (redundancy-aware) selection
- No selection (baseline)

### Evaluation Metrics
- Accuracy, Balanced Accuracy
- AUROC (Area Under ROC Curve)
- F1-Score, Sensitivity, Specificity
- Positive & Negative Predictive Value
- Adaptive Error Estimation

---

## 📊 Key Results

### Primary Dataset (BRFSS 2019) — Best Model: CatBoost
| Metric | Value |
|---|---|
| Accuracy | 0.870 |
| AUROC | 0.848 |
| Balanced Accuracy | 0.60 |
| F1-Score | 0.63 |
| Sensitivity | 0.23 |
| Specificity | 0.97 |

### Secondary Dataset (BRFSS 2020) — Best by Feature Group
| Feature Group | Best Model | Accuracy |
|---|---|---|
| Demographics | Random Forest | 0.866 |
| Lifestyle | Random Forest | 0.867 |
| General Health | LightGBM | 0.866 |
| Female Only | CatBoost | **0.909** |

### Key Findings
- Tree-based models (CatBoost, LightGBM, Random Forest) 
  consistently outperform simpler models
- Class imbalance causes high specificity but low sensitivity 
  across all models
- Full feature set produces the strongest predictive performance
- Key predictors: **high blood pressure, high cholesterol, BMI, 
  physical inactivity**
- GANDALF underperformed compared to ensemble methods except 
  in the female-only subgroup

---

## 🛠️ Technologies & Tools

| Category | Tools / Libraries |
|---|---|
| Language | Python 3 |
| ML Framework | df-analyze |
| Models | CatBoost, LightGBM, Random Forest, GANDALF, KNN, LR |
| Validation | 5-Fold Cross-Validation, Holdout Testing |
| Evaluation | scikit-learn, AUROC, Adaptive Error Estimation |
| Dataset | BRFSS 2019 & 2020 (CDC) |

---

## 📂 Repository Structure

> ⚠️ Raw BRFSS dataset files are not included due to size.  
> Download from: https://www.cdc.gov/brfss/annual_data/annual_2019.html

---

## 📬 Contact

**GitHub:** [@GayathriThirumoorthi](https://github.com/)
