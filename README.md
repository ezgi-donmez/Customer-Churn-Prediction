# Customer Churn Prediction

## Project Overview
This project focuses on predicting customer churn for an e-commerce company using machine learning and transforming the model results into actionable business insights.

The main goal is not only to identify which customers are likely to churn, but also to understand **why** they churn. This is especially important for business teams because churn prevention strategies should be based on customer behavior patterns rather than prediction alone.

In this study, the dataset was cleaned, explored, and modeled using multiple supervised learning algorithms. The final output combines predictive performance with managerial interpretation so that the results can support customer retention decisions.

---

## Business Problem
Customer churn is a major challenge for online retailers because losing an existing customer is often more costly than retaining one. For this reason, the company wants to:

- predict whether a customer is likely to churn,
- identify the main variables associated with churn,
- understand whether churn drivers differ across customer groups,
- generate insights that can support retention campaigns and promotional strategies.

This project approaches the problem as a **binary classification task**, where the target variable is `Churn` and takes values of `0` or `1`.

---

## Project Objectives
The project has two main objectives:

1. **Build reliable machine learning models** to predict customer churn.
2. **Extract interpretable business insights** that explain the possible drivers of churn.

More specifically, the analysis aims to answer questions such as:

- Which customers are at higher risk of churn?
- Which behavioral or demographic features are most related to churn?
- Are complaints, tenure, payment behavior, or product preferences associated with customer loss?
- What actions can the company take to reduce churn?

---

## Dataset
The dataset used in this project is the e-commerce customer churn dataset provided in the homework.

### Example feature groups
- **Customer behavior:** Tenure, DaySinceLastOrder, OrderCount, CouponUsed
- **Customer experience:** SatisfactionScore, Complain, WarehouseToHome
- **Financial / loyalty factors:** CashbackAmount, PreferredPaymentMode
- **Customer profile:** Gender, MaritalStatus, PreferredLoginDevice, PreferedOrderCat

---

## Data Preparation
Before modeling, the dataset was cleaned and prepared carefully.

### Main preprocessing steps
- Missing values were identified and handled.
- Numeric missing values were filled using **median imputation**.
- Inconsistent category labels were standardized.
- Categorical variables were transformed into machine-readable format using **one-hot encoding**.
- `CustomerID` was removed from modeling because it is an identifier and does not carry predictive meaning.
- The data was split into **training** and **test** sets using **stratification** to preserve the churn ratio.
- Standardization was applied where appropriate, especially for Logistic Regression.

### Data quality checks
- No duplicated rows were found.
- No repeated `CustomerID` values were found.
- Category inconsistencies such as different labels referring to the same concept were corrected before analysis.

---

## Exploratory Data Analysis
Exploratory data analysis was performed to understand the structure of churn and identify possible churn drivers before training the models.

### Main EDA focus areas
- churn rate across categorical features,
- distribution differences between churned and non-churned customers,
- numeric variable comparisons,
- correlation analysis among numerical features.

### Initial observations
The analysis suggested that churn is not random. It appears to be related to several customer behavior and experience variables, especially:

- tenure,
- complaint history,
- cashback amount,
- recency of ordering,
- payment mode,
- preferred order category.

These findings motivated the modeling stage and later supported the business interpretation section.

---

## Models Used
Four supervised classification models were trained and compared:

1. **Logistic Regression**
2. **Decision Tree**
3. **Random Forest**
4. **Gradient Boosting**

### Why multiple models?
Using several models made it possible to compare:
- linear vs. non-linear approaches,
- simpler vs. more flexible classifiers,
- interpretability vs. predictive power.

This comparison also helped determine which model provides the best balance between recall, precision, and overall classification quality.

---

## Model Evaluation
Because the target variable is moderately imbalanced, model evaluation did not rely only on accuracy. Instead, the following metrics were used:

- **Accuracy**
- **Precision**
- **Recall**
- **F1-score**
- **ROC-AUC**

Confusion matrices were also examined to understand:
- how many churners were correctly identified,
- how many churners were missed,
- how many false alarms were generated.

---

## Results
Among the tested models, **Gradient Boosting** achieved the best overall performance.

### Best-performing model
**Gradient Boosting**
- Accuracy: **95.8%**
- Precision: **0.9333**
- Recall: **0.8105**
- F1-score: **0.8676**
- ROC-AUC: **0.9877**

### Performance summary
- **Logistic Regression** and **Decision Tree** achieved relatively high recall, but their precision was lower.
- **Random Forest** performed very strongly and caught slightly more churners.
- **Gradient Boosting** produced the best overall balance and generated the fewest false positives.

This means that Gradient Boosting was the most efficient model when the goal is to identify churn risk while avoiding too many unnecessary interventions.

---

## Feature Importance
Feature importance analysis was performed using tree-based models.

### Most influential variables
The most important churn-related variables were:

- **Tenure**
- **CashbackAmount**
- **Complain**
- **DaySinceLastOrder**
- **WarehouseToHome**
- **SatisfactionScore**
- **NumberOfAddress**

### Interpretation
The feature importance results suggest that churn is mostly shaped by:
- customer lifecycle stage,
- complaint behavior,
- reward level,
- recent activity,
- customer experience quality.

Importantly, both Random Forest and Gradient Boosting pointed to a very similar ranking of important variables, which strengthens confidence in the interpretation.

---

## Business Insights
One of the main strengths of this project is that it goes beyond prediction and provides business-oriented explanations.

### 1. Early-stage customers are at the highest risk
Customers in their first months show the highest churn rate by a large margin. This indicates that churn is especially an **early-stage retention problem**.

**Business implication:**  
The first 90 days are critical. The company should invest in onboarding, welcome campaigns, and early engagement strategies.

---

### 2. Complaints are a strong warning signal
Customers who submitted complaints churn much more frequently than those who did not.

**Business implication:**  
Complaints should be treated as churn alerts. Faster complaint resolution and targeted retention actions may reduce customer loss.

---

### 3. Single customers appear more vulnerable
Churn is noticeably higher among single customers than among married customers.

**Business implication:**  
Retention strategy should be segmented. Single customers may respond better to personalized offers, loyalty incentives, or referral-based campaigns.

---

### 4. Mobile Phone buyers stand out as a risky segment
Customers whose preferred order category is Mobile Phone show relatively higher churn.

**Business implication:**  
This group may be more price-sensitive or more likely to compare competitors. Warranty extensions, post-purchase offers, and price-related campaigns may improve retention.

---

### 5. Low cashback and Cash on Delivery are linked to higher churn
Customers in lower cashback tiers and customers using Cash on Delivery tend to churn more.

**Business implication:**  
Reward design matters. Increasing cashback attractiveness and encouraging more stable digital payment methods may help reduce churn.

---

## Conclusion
This project shows that customer churn can be predicted effectively with machine learning while also generating meaningful business insights.

The results suggest that churn is not driven by a single variable. Instead, it is shaped by a combination of customer lifecycle, complaint behavior, engagement level, and loyalty-related features.

Overall, the analysis indicates that the company should move away from a one-size-fits-all retention strategy and focus more on:
- new customers,
- customers with complaints,
- single customers,
- Mobile Phone buyers,
- customers with weak reward engagement,
- high-risk payment groups.

From a modeling perspective, **Gradient Boosting** was selected as the best-performing approach for this project.
