# NovoTel: Telecom Churn Analysis

## Executive Summary
This project focuses on understanding and analyzing customer churn for NovaTel, a telecom service provider. Customer churn, when subscribers discontinue services is one of the biggest challenges in the telecom industry.

Through detailed exploratory data analysis (EDA), this project identifies the key reasons customers leave and highlights patterns that help the business improve retention. This phase includes:
- Cleaning and preparing the dataset
- Performing univariate, bivariate, and correlation analysis
- Deriving actionable insights
- Answering business-critical questions

## Project Overview
The goal of the NovaTel Churn Analysis project is to understand why customers churn and identify the most influential factors behind their decisions. Using the publicly available Telco Customer Churn Dataset, we analyze customer profiles, billing, service usage, contract types, and payment behaviors.

This analysis lays the foundation for building a predictive machine learning model that will help NovaTel proactively prevent churn.

## Business Problem
Telecom companies lose significant revenue when customers discontinue services. Acquiring a new customer costs 5–7× more than retaining an existing one. NovaTel wants to:

- Understand which customer groups are most at risk
- Identify factors causing churn
- Improve customer retention strategies
- Build a churn prediction model (coming in next version)

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
5. **Insight Generation**- Summarized all findings into clear insights, answered business questions, and formed actionable recommendations for reducing churn.

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

<img src="Visualizations/Univariate Analysis (Numerical Columns).png" width="100%" />

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

<img src="Visualizations/Histogram Plots.png" width="100%" />

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

<img src="Visualizations/Bivariate Analysis (Categorical).png" width="100%" />

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

<img src="Visualizations/Bivariate Analysis (Numerical).png" width="100%" />

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

<img src="Visualizations/Correlation Heatmap.png" width="100%" />

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

<img src="Visualizations/Heatmap (All Features).png" width="100%" />

</td>
</tr>
</table>


## Answers to Business Questions
1. What percentage of NovaTel customers churn, and how serious is the issue?
   - The overall churn rate is ≈ 26–28% (typical for this dataset).
   - This is high for a telecom company, where healthy churn is usually below 10%.
   - Indicates a serious retention problem requiring immediate intervention.

2. Which segments of customers churn the most? (Based on categorical + numerical bivariate analysi)
   - Senior citizens churn more than younger customers.
   - Short-tenure customers (<12 months) are the MOST likely to churn.
   - Customers living alone (No Partner / No Dependents) show higher churn.
   - Gender does not significantly impact churn, both similar.

3. How does contract type impact churn?
   - Month-to-month customers have the highest churn (very high risk group).
   - 1-year and 2-year contract customers churn far less, meaning long-term plans increase loyalty.
   - Contract type is one of the strongest churn predictors.

4. Do customers with higher monthly charges tend to leave more?
   - Churned customers show higher MonthlyCharges on average.
   - Many high-bill customers are fiber optic users or have multiple add-ons, increasing dissatisfaction.

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
- Libraries: Pandas, NumPy, Seaborn, Matplotlib, Scikit-learn

Thanks to the open-source community for tools and support ❤️
