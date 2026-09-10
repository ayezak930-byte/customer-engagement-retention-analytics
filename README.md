# Customer Engagement & Product Utilization Analytics for Retention Strategy

## Project Overview

Customer retention is an important challenge in the banking sector. This project analyzes customer engagement, product utilization, demographic, financial, and behavioral information to identify customers who are at higher risk of churn.

Machine learning techniques are used to predict customer churn and segment customers according to their risk level. A Power BI dashboard is developed to present the findings and support data-driven customer retention strategies.

## Objectives

- Analyze customer behavior and engagement patterns.
- Identify factors associated with customer churn.
- Analyze product utilization and customer activity.
- Develop machine learning models for churn prediction.
- Compare Logistic Regression and Random Forest performance.
- Identify high-risk customers using predicted churn probability.
- Develop a Power BI dashboard for customer risk analysis.
- Suggest retention strategies based on analytical findings.

## Dataset

The dataset contains 10,000 customer records and 14 variables.

### Variables

- Year
- CustomerId
- Surname
- CreditScore
- Geography
- Gender
- Age
- Tenure
- Balance
- NumOfProducts
- HasCrCard
- IsActiveMember
- EstimatedSalary
- Exited

`Exited` is the target variable:

- `0` = Retained Customer
- `1` = Churned Customer

## Data Preparation

The following preprocessing steps were performed:

- Checked missing values.
- Checked duplicate records.
- Removed identifier variables from modeling.
- Removed the constant `Year` variable.
- Applied One-Hot Encoding to categorical variables.
- Split the data into training and testing sets using an 80:20 ratio.
- Used stratified sampling for the train-test split.
- Applied feature scaling for Logistic Regression.

## Exploratory Data Analysis

EDA was performed to understand customer churn and engagement patterns.

The analysis covered:

- Customer retention and churn
- Customer activity
- Number of products
- Geography
- Age groups
- Gender
- Credit score
- Balance
- Estimated salary
- Tenure
- Product utilization
- Activity and product combinations
- Geography and activity relationships

### Key Findings

- Overall churn rate was **20.37%**.
- Inactive customers showed higher churn than active customers.
- Customers with one product showed considerably higher churn than customers with two products.
- Germany showed a higher churn rate than France and Spain.
- Customers aged 46–55 showed particularly high churn.
- Age and balance had positive relationships with churn.
- Customer activity showed a negative relationship with churn.

## Machine Learning

Two machine learning models were developed:

1. Logistic Regression
2. Random Forest

### Model Performance

| Model | Accuracy | Precision | Recall | F1-Score | ROC-AUC |
|---|---:|---:|---:|---:|---:|
| Logistic Regression | 80.80% | 58.91% | 18.67% | 28.36% | 77.48% |
| Random Forest | 86.15% | 78.76% | 43.73% | 56.24% | 85.53% |

Random Forest outperformed Logistic Regression across the main evaluation metrics and was selected as the primary predictive model.

## Churn Threshold Analysis

Different probability thresholds were evaluated to improve the identification of potential churners.

| Threshold | Precision | Recall | F1-Score |
|---|---:|---:|---:|
| 0.30 | 59.42% | 65.11% | 62.13% |
| 0.40 | 69.65% | 53.56% | 60.56% |
| 0.50 | 79.04% | 44.47% | 56.92% |
| 0.60 | 84.24% | 34.15% | 48.60% |

A threshold of **0.30** was selected because it provided the highest recall and F1-score among the tested thresholds.

At the 0.30 threshold:

- Accuracy: **83.85%**
- Precision: **59.42%**
- Recall: **65.11%**
- F1-Score: **62.13%**

## Feature Importance

The Random Forest model identified the following features as important for churn prediction:

1. Age
2. Balance
3. Estimated Salary
4. Credit Score
5. Number of Products
6. Tenure
7. Is Active Member
8. Geography
9. Gender
10. Has Credit Card

These results highlight the importance of customer characteristics, financial variables, engagement, and product-related information in predicting churn risk.

## Customer Risk Segmentation

Risk segmentation was performed on the **2,000 customers in the test dataset** using predicted churn probabilities.

| Risk Level | Customers | Percentage |
|---|---:|---:|
| Low Risk | 1,565 | 78.25% |
| Medium Risk | 275 | 13.75% |
| High Risk | 160 | 8.00% |

### High-Risk Customer Profile

The high-risk segment contains **160 customers**.

Key characteristics include:

- Average age: **49.29 years**
- Average balance: **95,854.51**
- Average credit score: **643.47**
- Inactive customers: **125**
- Active customers: **35**

High-risk customers by geography:

- Germany: **86**
- France: **48**
- Spain: **26**

The 46–55 age group represented the largest portion of the high-risk segment.

## Retention Strategy

Based on the analytical findings, the following retention strategies are recommended:

### 1. Re-engage Inactive Customers

Inactive customers should be prioritized through personalized communication and relevant engagement initiatives.

### 2. Focus on High-Risk Customers

Customers with high predicted churn probability should receive priority for retention interventions.

### 3. Improve Product Utilization

Customers with limited product utilization can be targeted with suitable product engagement and cross-selling initiatives.

### 4. Geographic Focus

Germany requires particular attention because of its comparatively higher churn levels and larger high-risk customer segment.

### 5. Age-Based Retention

The 46–55 customer segment should receive focused engagement and retention initiatives.

### 6. Predictive Monitoring

The churn prediction model can be used to identify customers whose predicted churn risk increases over time.

## Power BI Dashboard

A Power BI dashboard was developed to communicate the analytical results.

### Dashboard Pages

#### Executive Overview

Provides a high-level view of:

- High-risk customers
- Churned customers
- Customer risk distribution
- High-risk customers by geography
- High-risk customers by activity

#### Risk Analysis

Provides detailed analysis of high-risk customers based on:

- Number of products
- Credit score
- Age group
- Balance
- Tenure
- Gender
- Product and activity combination

#### Customer Risk Profile

Provides additional analysis of high-risk customer characteristics and engagement patterns.

## Tools & Technologies

- Python
- Google Colab
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- Random Forest
- Logistic Regression
- Power BI
- Microsoft Word

## Project Files

- `Research_Paper.pdf` – Complete research paper
- `Customer_Engagement_Retention_Analytics.pbix` – Power BI dashboard
- `Final_Customer_Risk_Dataset.csv` – Customer risk dataset
- `Customer_Churn_Analysis.ipynb` – Python analysis and machine learning workflow
- `README.md` – Project documentation

## Conclusion

This project demonstrates how customer engagement and product utilization analytics can be combined with machine learning to support customer retention in banking.

Random Forest achieved an ROC-AUC of **85.53%** and outperformed Logistic Regression. A probability threshold of **0.30** improved churn detection, achieving **65.11% recall** and an F1-score of **62.13%**.

The resulting customer risk segmentation and Power BI dashboard provide a practical analytical framework for identifying high-risk customers and supporting targeted retention strategies.
