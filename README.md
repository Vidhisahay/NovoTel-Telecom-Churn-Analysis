# NovoTel: Telecom Churn Analysis

## Executive Summary
This project focuses on understanding and analyzing customer churn for NovaTel, a telecom service provider. Customer churn, when subscribers discontinue services is one of the biggest challenges in the telecom industry.

Through detailed exploratory data analysis (EDA), this project identifies the key reasons customers leave and highlights patterns that help the business improve retention. This phase includes:
- Cleaning and preparing the dataset
- Performing univariate, bivariate, and correlation analysis
- Deriving actionable insights
- Answering business-critical questions

In addition to analytics, this version of the project also includes a Machine Learning (ML) churn prediction model to classify at-risk customers.

![Dashboard](https://github.com/Vidhisahay/NovoTel-Telecom-Churn-Analysis/blob/main/Visualizations/Analytics/Dashboard%20Mockup.png)

## Project Overview
The goal of the NovaTel Churn Analysis project is to understand why customers churn and identify the most influential factors behind their decisions. Using the publicly available Telco Customer Churn Dataset, we analyze customer profiles, billing, service usage, contract types, and payment behaviors.

This analysis lays the foundation for building and evaluating a predictive machine learning model that helps NovaTel proactively prevent churn.

## Business Problem
Telecom companies lose significant revenue when customers discontinue services. Acquiring a new customer costs 5–7× more than retaining an existing one. NovaTel wants to:

- Understand which customer groups are most at risk
- Identify factors causing churn
- Improve customer retention strategies
- Build a churn prediction model

The insights from this analysis will support NovaTel in making data-driven decisions to reduce churn and improve customer satisfaction.

## Dataset & Source
**Dataset:** Telco Customer Churn Dataset <br>
**Rows:** 7,000+ customer records <br>
**Columns:** 20+ customer attributes including:

- **Demographics:** gender, senior citizen, dependents
- **Account information:** tenure, contract type, payment method
- **Services used:** internet, security, backup, streaming, tech support
- **Billing details:** monthly charges, total charges
- **Target variable:** Churn (Yes/No)
- **Source:** [Kaggle](https://www.kaggle.com/datasets/blastchar/telco-customer-churn) 

## Methodology Used
1. **Data Cleaning & Preprocessing**- Handled missing values, corrected data types, scrubbed TotalCharges, and finalized a cleaned dataset.
2. **Univariate Analysis**- Explored individual feature distributions and summarized customer demographics using countplots and statistics.
3. **Bivariate Analysis**- Compared customer attributes against Churn and identified drivers using grouped summaries and visual aids like boxplots.
4. **Correlation & Pattern Detection**- Generated heatmaps and uncovered key patterns across tenure, contract terms, and service usage to assess relationships.
5. **Machine Learning Modeling**- Trained multiple models including Logistic Regression, Random Forest, XGBoost, SVM, KNN.
Built a soft Voting Classifier for best performance.
6. **Insight Generation**- Summarized all findings into clear insights, answered business questions, and formed actionable recommendations for reducing churn.

## Detailed Insights From Data Exploration

<table>
<tr>
<td width="55%" style="vertical-align: top;">

### Univariate Analysis of Numerical Features 
- Shows distribution of **tenure, MonthlyCharges, TotalCharges**  
- Mean & median lines help identify skewness  
- MonthlyCharges is right-skewed → high bill customers exist  
- Tenure shows steep drop → many new customers leave early  

</td>
<td width="45%" style="vertical-align: top;">

<img src="Visualizations/Analytics/Univariate Analysis (Numerical Columns).png" width="100%" />

</td>
</tr>
</table>

<table>
<tr>
<td width="55%" style="vertical-align: top;">

### Histograms of Numerical Features  
- Displays raw distribution patterns  
- Helps identify outliers or unusual density  
- Confirms skewness in TotalCharges  

</td>
<td width="45%" style="vertical-align: top;">

<img src="Visualizations/Analytics/Histogram Plots.png" width="100%" />

</td>
</tr>
</table>

<table>
<tr>
<td width="55%" style="vertical-align: top;">

### Categorical Features vs Churn  
- Month-to-month contracts show highest churn  
- Fiber optic users churn more than DSL  
- Electronic check users churn at very high rates  

</td>
<td width="45%" style="vertical-align: top;">

<img src="Visualizations/Analytics/Bivariate Analysis (Categorical).png" width="100%" />

</td>
</tr>
</table>

<table>
<tr>
<td width="55%" style="vertical-align: top;">

### Numerical Features vs Churn  
- Churned customers have **higher MonthlyCharges**  
- Tenure is the strongest churn indicator where  
  customers with <12 months churn the most  
- TotalCharges also significantly lower for churned customers  

</td>
<td width="45%" style="vertical-align: top;">

<img src="Visualizations/Analytics/Bivariate Analysis (Numerical).png" width="100%" />

</td>
</tr>
</table>

<table>
<tr>
<td width="60%" style="vertical-align: top;">

### Correlation Heatmap  
- Tenure and TotalCharges strongly positively correlated  
- MonthlyCharges moderately correlated with churn  
- No harmful multicollinearity detected  

</td>
<td width="45%" style="vertical-align: top;">

<img src="Visualizations/Analytics/Correlation Heatmap.png" width="100%" />

</td>
</tr>
</table>


<table>
<tr>
<td width="55%" style="vertical-align: top;">

### Combined Heatmap with All Features  
- Summarizes feature relationships  
- Confirms contract type, tenure, and monthly charges matter most  
- Payment method & internet service also show strong influence  

</td>
<td width="45%" style="vertical-align: top;">

<img src="Visualizations/Analytics/Heatmap (All Features).png" width="100%" />

</td>
</tr>
</table>



## Machine Learning Model Performance

<table style="width: 100%; max-width: 1000px; border-collapse: collapse; margin-bottom: 30px;">
<tr>
<td style="width: 40%; vertical-align: top; padding-right: 20px;">

### 1. Model Selection & Key Results

<p>The final model chosen for prediction was the <b>Voting Classifier (Soft Voting).</b></p>
<ul>
<li>Why Selected: This ensemble combines the strengths of Logistic Regression, Decision Tree, Random Forest, and XGBoost, resulting in a more stable and balanced predictive performance.</li>
<li>Final Accuracy: The model achieved an excellent overall accuracy of ~80.8%.</li>
<li>Evaluation Metrics: Evaluation included a comprehensive analysis using Accuracy, Precision, Recall, F1-Score, and ROC-AUC.</li>
</ul>

</td>
<td style="width: 60%; vertical-align: top; text-align: center;">
<img src="Visualizations/ML Models/ROC Curve Comparison.png" style="width: 100%; max-width: 600px; height: auto; border: 1px solid #ddd; box-shadow: 0 4px 8px rgba(0,0,0,0.2);" alt="Comparison of ROC curves for all tested classification models." />
</td>
</tr>
</table>

<table style="width: 100%; max-width: 1000px; border-collapse: collapse; margin-bottom: 30px;">
<tr>
<td style="width: 40%; vertical-align: top; padding-right: 20px;">

### 2. Final Model Confusion Matrix

<p>The Confusion Matrix is critical for interpreting the model's business value, especially concerning False Negatives (missed churn risk).</p>
<ul>
<li>Stable Customers (Non-Churn): Out of 1,549 actual non-churn customers, 1,399 were correctly predicted as staying.</li>
<li>Critical Misses (False Negatives): <b>255 actual churn customers were missed</b> by the model. This high volume of False Negatives highlights the need for improved Recall in future iterations.</li>
</ul>

</td>
<td style="width: 60%; vertical-align: top; text-align: center;">
<img src="Visualizations/ML Models/Voting Classifier Heatmap.png" style="width: 100%; max-width: 450px; height: auto; border: 1px solid #ddd; box-shadow: 0 4px 8px rgba(0,0,0,0.2);" alt="Confusion matrix heatmap for the final Voting Classifier, showing 255 False Negatives." />
</td>
</tr>
</table>

<table style="width: 100%; max-width: 1000px; border-collapse: collapse; margin-bottom: 30px;">
<tr>
<td style="width: 40%; vertical-align: top; padding-right: 20px;">

### 3. Feature Importance

<p>Feature importance, derived from the underlying tree-based models (Random Forest + XGBoost), confirms the validity of the initial EDA insights.</p>
<ul>
<li>Strongest Predictor: <b>TotalCharges</b> is confirmed as the single most influential factor in predicting churn, underscoring the early retention problem.</li>
<li>Service Gaps: The lack of security services (OnlineSecurity_No, TechSupport_No) and the presence of Fiber Optic service significantly increase churn probability.</li>
</ul>

</td>
<td style="width: 60%; vertical-align: top; text-align: center;">
<img src="Visualizations/ML Models/Feature Importance.png" style="width: 100%; max-width: 750px; height: auto; border: 1px solid #ddd; box-shadow: 0 4px 8px rgba(0,0,0,0.2);" alt="Bar chart detailing feature importance, confirming Tenure and Contract as top predictors." />
</td>
</tr>
</table>

## Answers to Business Questions
1. What percentage of customers show strong loyalty or stability?
    - Around **80%** are predicted as stable/loyal.  
    - Around **20%** fall into the “at-risk” category and require attention.  
    - This is meaningful but not alarming, intervention is worthwhile.

2. Which segments of customers churn the most? (Based on categorical + numerical bivariate analysis)
   - Senior citizens churn more than younger customers.
   - Short-tenure customers (<12 months) are the MOST likely to churn.
   - Customers living alone (No Partner / No Dependents) show higher churn.
   - Gender does not significantly impact churn, both similar.

3. How do product holdings impact loyalty?
    - More products → higher loyalty (cross-product stickiness)  
    - Single-product customers are the **most likely to churn**  
    - Product bundles significantly improve retention probability

4. Do higher deposit values correlate with loyalty?
    - Yes, **higher and stable deposits** strongly indicate long-term loyalty  
    - Low or inconsistent deposits predict attrition  
    - Stability > total balance for predicting customer behavior

5. Are there any patterns or correlations that stand out in customer behavior?
   - High monthly charges → higher churn
   - Long-term contracts → lower churn
   - High-dependency customers (partner, dependents) → lower churn
   - Internet service type strongly affects churn
   - Tenure is the most influential factor
   - High correlation between TotalCharges and tenure, meaning more loyal customers accumulate higher total bills but churn less.
  
## Business Recommendations
1. **Drive Long-Term Contracts:** Aggressively incentivize customers to move from high-churn month-to-month plans to more stable 1 or 2-year contracts by offering loyalty discounts.
2. **Enhance Early Customer Onboarding:** Focus retention efforts on the first 3-12 months. Assign onboarding support to new users and proactively address early service dissatisfaction to reduce low-tenure churn.
3. **Address High-Cost Churn:** Mitigate "bill shock" for high-paying and Fiber Internet customers. Offer transparent billing, bundled packages, and priority support to improve service value and satisfaction.
4. **Promote High-Retention Features:** Actively market add-on services like Online Security and Tech Support. Incentivize customers to switch from high-churn Electronic Checks to stable auto-pay or credit card payments.

## Acknowledgements
- Dataset: Telco Customer Churn Dataset from Kaggle
- Libraries: Python, Pandas, NumPy, Seaborn, Matplotlib, Scikit-learn
- Model: Voting Classifier (Final Accuracy: 80.8%)

Thanks to the open-source community for tools and support ❤️
