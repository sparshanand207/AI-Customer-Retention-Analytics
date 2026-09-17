# AI Customer Retention Analytics

## Project Overview

Customer churn is a major business challenge for subscription-based companies. This project develops a data-driven customer retention framework that uses machine learning to identify customers at higher risk of churn and translate those predictions into actionable retention strategies.

The analysis combines exploratory data analysis, predictive modeling, customer risk scoring, and business recommendations to help prioritize retention efforts.

---

## Business Problem

The goal of this project is to answer three key questions:

1. Which customer characteristics are associated with higher churn?
2. Can machine learning models predict customers who are at risk of churning?
3. How can predicted churn risk be translated into actionable customer retention strategies?

---

## Dataset

The project uses a telecommunications customer churn dataset containing:

- **7,043 customers**
- **21 customer-level variables**
- Demographic information
- Account and contract information
- Service usage information
- Payment information
- Monthly and total charges
- Customer churn status

Key variables include:

- `tenure`
- `MonthlyCharges`
- `TotalCharges`
- `Contract`
- `InternetService`
- `OnlineSecurity`
- `TechSupport`
- `PaymentMethod`
- `Churn`

---

## Tools & Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook
- Logistic Regression
- Random Forest
- Customer Risk Segmentation

---

## Analytical Approach

### 1. Data Preparation

- Loaded and inspected the customer dataset
- Reviewed data types and dataset structure
- Cleaned and converted relevant variables
- Prepared the data for machine learning
- Split the dataset into training and testing sets using stratification

### 2. Exploratory Data Analysis

The analysis examined relationships between churn and:

- Contract type
- Customer tenure
- Monthly charges
- Internet service
- Online security
- Technical support
- Payment method
- Other customer and service characteristics

### 3. Predictive Modeling

Two classification models were developed:

- Logistic Regression
- Random Forest

The models were evaluated using:

- Accuracy
- Precision
- Recall
- F1 Score
- ROC-AUC
- Confusion Matrix
- ROC Curve

### 4. Threshold Analysis

Different probability thresholds were evaluated to understand the trade-off between precision and recall.

This allows the retention strategy to be adjusted depending on whether the business wants to prioritize:

- Identifying more potential churners
- Reducing false positives
- Balancing retention outreach with available resources

### 5. Customer Risk Scoring

The final Random Forest model was used to generate predicted churn probabilities for customers.

Customers were segmented into:

- Low Risk
- Medium Risk
- High Risk

This creates a practical framework for prioritizing retention efforts.

---

## Model Performance

### Random Forest

| Metric | Performance |
|---|---:|
| Accuracy | 74.6% |
| Precision | 51.4% |
| Recall | 78.9% |
| F1 Score | 62.2% |
| ROC-AUC | 83.7% |

### Logistic Regression

| Metric | Performance |
|---|---:|
| Accuracy | 80.5% |
| Precision | 65.2% |
| Recall | 57.5% |
| F1 Score | 61.1% |
| ROC-AUC | 83.6% |

The two models provide different trade-offs between identifying churners and limiting false positives. The project therefore considers multiple evaluation metrics rather than relying on accuracy alone.

---

## Key Findings

### 1. Tenure is an important churn-related factor

Customer tenure was identified as the most important feature in the Random Forest model.

The analysis also found substantially higher historical churn among customers with shorter tenure compared with longer-tenured customers.

### 2. Contract type is strongly associated with churn

Month-to-month customers showed substantially higher historical churn than customers on longer-term contracts.

This suggests that contract structure can be an important consideration when designing retention strategies.

### 3. High-risk customers form a meaningful segment

Approximately 30.8% of customers were classified as high risk using the project's risk segmentation framework.

The average predicted churn probability for this group was approximately 76.9%.

### 4. High-risk customers show several recurring characteristics

Within the high-risk customer segment:

- Approximately 98.9% were on month-to-month contracts
- Approximately 76.2% used fiber optic internet
- Approximately 65.5% used electronic check as their payment method

These characteristics can be used to help prioritize customer outreach and retention analysis.

---

## Business Recommendations

Based on the analysis, several retention strategies can be considered:

### Early-Tenure Retention Program

Develop targeted onboarding and engagement programs for newer customers, since shorter-tenure customers showed higher historical churn.

### Contract Conversion Strategies

Test incentives or value-based offers designed to encourage eligible month-to-month customers to consider longer-term contracts.

### Targeted High-Risk Interventions

Use predicted churn probability to prioritize retention resources rather than applying the same intervention to every customer.

### Payment Experience Review

Investigate whether customers using electronic check experience payment-related friction and evaluate whether alternative payment options could improve retention.

### Service and Support Engagement

Evaluate opportunities to proactively engage high-risk customers with relevant support, service education, or account assistance.

---

## Limitations

This analysis has several limitations:

- Predictions are based on historical customer behavior.
- The model identifies predictive associations and does not establish that individual factors cause churn.
- Model probabilities should be validated using future customer data before operational deployment.
- Retention strategies should be tested using controlled experiments or A/B testing.
- Model performance may change as customer behavior and business conditions change.

---

## Next Steps

Potential improvements and future work include:

- Validate the model on future customer data.
- Periodically retrain the model as new customer data becomes available.
- Monitor model performance over time.
- Test different retention strategies across customer risk segments.
- Measure actual retention lift from targeted campaigns.
- Compare campaign costs with incremental customer value to evaluate retention ROI.

---

## Project Outcome

This project demonstrates how customer-level data and machine learning can be transformed into a practical customer retention framework.

Rather than stopping at churn prediction, the analysis converts predicted churn probabilities into customer risk segments that can support targeted retention decision-making.

The resulting framework connects:

**Customer Data → Churn Analysis → Machine Learning → Risk Scoring → Customer Segmentation → Retention Strategy**

---

## Repository Structure

```text
AI-Customer-Retention-Analytics/
│
├── data/
│   └── WA_Fn-UseC_-Telco-Customer-Churn.csv
│
├── notebooks/
│   └── AI_Customer_Retention_Analytics.ipynb
│
├── README.md
├── requirements.txt
└── .gitignore