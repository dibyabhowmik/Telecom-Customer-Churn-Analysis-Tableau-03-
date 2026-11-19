# Customer Churn Analysis

## Project Overview

**Customer Churn Analysis** is a Tableau project focused on understanding customer churn in the telecommunications industry. The project analyzes customer demographics, tenure, internet services, security services, technical support, contract type, payment methods, monthly charges, and other customer characteristics to identify groups with different churn rates.

The dataset contains **7,043 customers and 21 fields**.

## Objectives

1. Calculate the overall customer churn rate.
2. Identify customer groups with higher churn.
3. Analyze churn across contract types.
4. Compare churn across internet service types.
5. Understand the relationship between tenure and churn.
6. Examine the effect of monthly charges on churn.
7. Analyze churn by payment method.
8. Study the relationship between additional services and churn.
9. Compare churn across demographic characteristics.
10. Identify combinations of customer characteristics associated with higher churn.

## Tools & Techniques Used

- Tableau Public
- Telecom customer churn dataset
- Data preparation
- Calculated fields
- Customer segmentation
- Churn-rate analysis
- Bar charts
- Heatmaps
- KPI cards
- Filters
- Aggregation
- Comparative analysis
- Dashboard-oriented visualization

## Data Preparation & Process

The dataset was first checked for appropriate data types and consistency.

A **Churn Flag** was created to convert the Yes/No churn field into a numerical measure.

### Calculated Fields

**1. Churn Flag**

```tableau id="f7m2kd"
IF [Churn] = "Yes" THEN 1 ELSE 0 END
```

A churn-rate calculation was also created:

**2. Churn Rate**

```tableau id="v9p4xa"
SUM([Churn Flag]) / COUNT([customerID])
```

For tenure analysis, customers were grouped into meaningful tenure bands.

**3. Tenure Group**

```tableau id="t6n3qb"
IF [tenure] <= 12 THEN "0–12 Months"
ELSEIF [tenure] <= 24 THEN "13–24 Months"
ELSEIF [tenure] <= 48 THEN "25–48 Months"
ELSE "49+ Months"
END
```

The analysis then compared churn rates across contract type, internet service, technical support, online security, payment method, tenure, senior-citizen status, gender, partner status, dependents, and phone service.

A **Contract × Payment Method** heatmap was also created to examine combined customer characteristics.

## Key Insights

1. Overall customer churn in the dataset is approximately **26.5%**.
2. Month-to-month customers have substantially higher churn than customers on one-year or two-year contracts.
3. Two-year contract customers show the lowest churn
