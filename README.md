# Customer Purchase Behavior Analysis

## Problem Statement
Welcome to this Probability and Statistics project! In this project, we analyze a real-world dataset containing customer information and purchasing behavior from a marketing campaign. The goal is to uncover patterns, trends, and correlations to help optimize marketing strategies and boost offer acceptance rates.

## Objective
The mission is to:
- Analyze customer data to identify key insights.
- Use descriptive statistics to understand purchasing behavior.
- Segment customers for targeted marketing efforts.

## Dataset Overview
The dataset, collected from last year's campaign, includes the following features:

- **Response (target):** 1 if the customer accepted the offer, 0 otherwise.
- **ID:** Unique customer identifier.
- **Year_Birth:** Customer's birth year.
- **Complain:** 1 if the customer complained in the last 2 years.
- **Dt_Customer:** Date of customer enrollment.
- **Education:** Customer’s education level.
- **Marital_Status:** Customer’s marital status.
- **Kidhome:** Number of small children in the household.
- **Teenhome:** Number of teenagers in the household.
- **Income:** Yearly household income.
- **MntXXXProducts:** Amount spent on fish, meat, fruits, sweets, wines, and gold products over 2 years.
- **NumXXXPurchases:** Purchases made via deals, catalog, store, or web.
- **NumWebVisitsMonth:** Website visits in the last month.
- **Recency:** Days since the last purchase.

## Setup Instructions
### Prerequisites
- Python 3.x
- Libraries: `pandas`, `numpy`, `matplotlib`, `seaborn`, `sklearn`, `scipy`
- Google Colab (optional, for running with Google Drive)


## Data Cleaning
- **Missing Values:** Filled 24 missing Income values with the mean using `SimpleImputer`.
- **Data Types:** Converted `Dt_Customer` to datetime, `Education` and `Marital_Status` to categorical.
- **Outliers:** Replaced extreme `Year_Birth` values (ages > 120) with the median; corrected an anomalous `Income` value (666,666) with the mean.
- **New Features:** Added `Total_spending` (sum of all product spends) and `Customer_age` (current year - `Year_Birth`).

## Exploratory Data Analysis (EDA)
### Key Visuals
#### Marital Status Distribution
![Marital Status Bar](#) <!-- Replace with actual plot -->
Most customers are Married or Together.

#### Education Levels
![Education Bar](#) <!-- Replace with actual plot -->
Majority are Graduates, followed by PhDs.

#### Income Distribution
![Income Histogram](#) <!-- Replace with actual plot -->
Right-skewed, with outliers handled.

#### Kids and Teens
Over 50% of households have no kids or teens.

## Statistical Findings
### Central Tendency
| Metric         | Customer_age | Income  | Education  | Marital_Status |
|--------------|--------------|---------|------------|---------------|
| Mean        | 55           | 52,167.82 | N/A        | N/A           |
| Median      | 54           | 51,315   | N/A        | N/A           |
| Mode        | 49           | 52,247.25 | Graduation | Married       |

### Dispersion
- **Standard Deviation:** Age = 11.99, Income = 25,070.92
- **Variance:** Age = 143.76, Income = 628,550,740.62

### Probability Distributions
- **Binomial (Response):** Expected responses = 334, Probability of 300 responses = 0.0135.
- **Normal (Income):** Probability of income < 40,000 = 0.31.

## Customer Segmentation
- **Method:** K-Means clustering with 3 clusters (chosen via Elbow Method).
- **Features:** Numerical (e.g., Income, Total_spending) + encoded categorical (Education, Marital_Status).

### Visualization
![image](https://github.com/user-attachments/assets/f961a197-9c61-44d7-a34f-0d24a2e7bac6)


### Cluster Insights
| Cluster | Income (Avg) | Total_spending (Avg) | Key Traits |
|---------|-------------|--------------------|-------------|
| 0       | 35,000      | 150                | Lower income, low spenders |
| 1       | 70,000      | 1,200              | High income, high spenders |
| 2       | 50,000      | 600                | Moderate income, moderate spenders |

## Conclusions & Recommendations
### Targeting High Spenders (Cluster 1):
- Focus marketing on high-income customers (avg $70K) who spend heavily on wines and meat.
- Offer premium product discounts or loyalty rewards.

### Engaging Moderate Spenders (Cluster 2):
- Target graduates and married customers with family-oriented promotions (e.g., deals on fruits, sweets).

### Low Spenders (Cluster 0):
- Use cost-effective channels (e.g., web) to offer deals, as they’re price-sensitive (high `NumDealsPurchases`).

### Complaint Handling:
- Customers who complain spend less—investigate dissatisfaction causes (e.g., delivery, quality).

## Bonus Task: Geogebra Experiment
**Description:** A simulation of coin flips to explore binomial distributions.

**Video Link**
https://drive.google.com/file/d/1GVoZHRTC0ejUGTrFbpo4rFc0li3VdyR7/view?usp=sharing
