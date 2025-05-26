# Customer Churn Analysis in Banking

A data science project focused on identifying the drivers behind customer churn at a retail bank using statistical methods and predictive modeling. 

---

## Objective

To perform exploratory data analysis (EDA), hypothesis testing, and build predictive models to answer:

- What features significantly influence customer churn?
- How does customer geography relate to key financial indicators?
- Can churn be reliably predicted using logistic regression?

---

## Dataset

**Source**: [Kaggle - Banking Customer Churn Prediction Dataset](https://www.kaggle.com/)  
**Records**: 10,000  
**Features**: 14  
**Target**: `Exited` (1 = churned, 0 = stayed)

**Feature categories**:
- **Numerical**: `CreditScore`, `Age`, `Balance`, `Tenure`, `EstimatedSalary`, `NumOfProducts`
- **Categorical**: `Gender`, `Geography`, `HasCrCard`, `IsActiveMember`, `Exited`

Preprocessing steps included:
- Dropping irrelevant ID columns (`RowNumber`, `CustomerId`, `Surname`)
- Confirming no missing or duplicate values

---

## Analysis Overview

### EDA
- Histograms, boxplots, and bar charts to assess variable distributions
- Summary statistics for all numerical features
- Class imbalance: ~20% churned, ~80% retained

### Statistical Tests
- **Levene’s Test**: Verified equal variances assumption
- **Welch’s T-Test**: Compared means between churned vs non-churned
- **Chi-square Test**: Categorical variable independence
- **ANOVA** & **Post-hoc Tests**:
  - Geography vs Balance, Age, and Credit Score
  - Games-Howell & Tukey tests for group comparison
### Correlation Analysis
- Pearson correlation matrix & heatmap
- Key finding: Age positively correlated with churn; active membership negatively correlated
---

## Predictive Modeling

### Multivariate Linear Regression
- Model 1: Predict `Balance`
- Model 2: Predict `Age`
- Included encoded geography variables (`Germany`, `Spain`)
- Identified key predictors using t-tests
- R² for `Balance`: 0.25  
  R² for `Age`: 0.10

### Logistic Regression
- Predicting `Exited` (Churn)
- Used `class_weight='balanced'` due to class imbalance
- Evaluation:
  - Accuracy: **69%**
  - AUC Score: **0.741**
  - Confusion Matrix + Classification Report
  - ROC Curve visualization

### Lasso Regression
- Applied for feature selection and regularization
- Identified top predictors: `Age`, `IsActiveMember`, `Geography_Germany`
- Visualized coefficients for interpretability

---

## Files

| File | Description |
|------|-------------|
| `PROJECT.ipynb` | Jupyter Notebook with code and visualizations |
| `Project Report.docx` | Detailed project report with explanations and interpretations |

---

## Key Insights

- Older and inactive customers are more likely to churn
- Geography (especially customers in Germany) plays a key role in churn
- Predictive models like Logistic Regression and Lasso provide interpretable baselines
- Business strategies can be tailored using statistical and model-driven insights

---

