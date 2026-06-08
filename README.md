# Marketing Campaign Performance & Customer Conversion Analysis

## 📌 Project Overview

Businesses often run multiple marketing campaigns but struggle to understand:

- Which campaigns generate the highest conversions
- Which customer segments are most valuable
- Which sales channels perform best

This project analyzes customer demographics, purchasing behavior, campaign responses, and sales channel performance to uncover actionable insights that can improve marketing ROI and customer targeting strategies.

---

## 🎯 Problem Statement

The goal of this project is to analyze customer and campaign data to:

- Identify high-value customer segments
- Evaluate marketing campaign effectiveness
- Compare sales channel performance
- Discover spending patterns across customer groups
- Provide data-driven business recommendations

---

## 📂 Dataset Information

**Source:** Kaggle Customer Personality Analysis Dataset

The dataset contains customer demographic information, purchasing behavior, campaign responses, and sales channel activity.

### Customer Demographics

| Column | Description |
|----------|-------------|
| ID | Unique customer identifier |
| Year_Birth | Customer birth year |
| Education | Education level |
| Marital_Status | Marital status |
| Income | Annual household income |
| Kidhome | Number of children |
| Teenhome | Number of teenagers |
| Dt_Customer | Customer enrollment date |

### Product Spending Behavior

| Column | Description |
|----------|-------------|
| MntWines | Wine spending |
| MntFruits | Fruit spending |
| MntMeatProducts | Meat spending |
| MntFishProducts | Fish spending |
| MntSweetProducts | Sweet spending |
| MntGoldProds | Premium product spending |

### Marketing Campaign Response

| Column | Description |
|----------|-------------|
| AcceptedCmp1 | Campaign 1 response |
| AcceptedCmp2 | Campaign 2 response |
| AcceptedCmp3 | Campaign 3 response |
| AcceptedCmp4 | Campaign 4 response |
| AcceptedCmp5 | Campaign 5 response |
| Response | Most recent campaign response |

### Sales Channel Behavior

| Column | Description |
|----------|-------------|
| NumDealsPurchases | Discount purchases |
| NumWebPurchases | Online purchases |
| NumCatalogPurchases | Catalog purchases |
| NumStorePurchases | Store purchases |
| NumWebVisitsMonth | Monthly website visits |

### Customer Feedback

| Column | Description |
|----------|-------------|
| Recency | Days since last purchase |
| Complain | Complaint flag |

### Excluded Fields

The following fields were excluded from analysis:

- Z_CostContact
- Z_Revenue

---

## 🛠️ Tools Used

- Microsoft Excel
- Excel Charts & Visualizations
- Google Docs

---

## 🧹 Data Cleaning Process

### Data Preparation

- Created backup dataset
- Renamed sheets:
  - RAW_DATA
  - CLEANED_DATA
- Performed all transformations on the cleaned dataset

### Removed Irrelevant Columns

- Z_CostContact
- Z_Revenue

### Duplicate Check

```excel
=IF(COUNTIF($A$2:$A$2241, A2) > 1, "Duplicate", "Unique")
```

**Result:** No duplicates found.

### Missing Value Treatment

| Column | Method |
|----------|----------|
| Income | Median Imputation |
| Marital_Status | Unknown |
| Education | Unknown |

---

## ⚙️ Feature Engineering

### Marital Status Standardization

```excel
=SWITCH(LOWER(TRIM(D2)),
"married","Married",
"together","In Relationship",
"single","Single",
"alone","Single",
"divorced","Divorced",
"widow","Widowed",
"yolo","Unknown",
"Unknown")
```

### Education Standardization

```excel
=SWITCH(LOWER(TRIM(E2)),
"graduation","Graduate",
"phd","PhD",
"master","Master",
"2n cycle","Master",
"basic","High School",
"Unknown")
```

### Date Processing

- Standardized date formats
- Converted dates to proper date type
- Extracted Enrollment Year
- Calculated Customer Tenure

```excel
=IF(ISNUMBER(S2), S2,
DATE(RIGHT(S2,4), MID(S2,4,2), LEFT(S2,2)))
```

### Age Calculation

```excel
=YEAR(TODAY()) - Year_Birth
```

### Total Spending

```excel
=SUM(MntWines:MntGoldProds)
```

### Total Purchases

```excel
=SUM(NumDealsPurchases:NumStorePurchases)
```

### Total Campaign Responses

```excel
=SUM(AcceptedCmp1:AcceptedCmp5)
```

### Customer Value Score

```excel
=Total_Spend + Total_Purchases + (Total_Campaigns_Accepted*100)
```

---

## 📊 Analysis Questions

### 1. Which Customer Segments Generate the Highest Revenue?

#### Revenue by Income Segment

- High-income customers contribute the highest revenue.
- Mid-income customers follow closely behind.
- Low-income customers contribute significantly less revenue.

#### Revenue by Age Segment

- Senior customers generate the highest total revenue.
- Seniors also represent the largest customer segment.

#### Purchase Behavior by Age

- Senior customers make the highest number of purchases.
- They demonstrate consistent buying behavior.

---

### 2. Which Sales Channels Perform Best?

Sales channel performance ranking:

1. Store Purchases
2. Web Purchases
3. Catalog Purchases
4. Deal-Based Purchases

**Insight:** Offline store purchases dominate customer buying behavior.

---

### 3. Which Marketing Campaigns Have the Highest Acceptance Rate?

| Campaign | Performance |
|-----------|-------------|
| Campaign 4 | Highest |
| Campaign 3 | Strong |
| Campaign 5 | Strong |
| Campaign 1 | Moderate |
| Campaign 2 | Lowest |

**Insight:** Campaign 4 is the most successful campaign.

---

### 4. What Is the Relationship Between Income and Spending?

- Higher-income customers consistently spend more.
- Income is positively correlated with customer spending.
- Premium marketing strategies may perform well among high-income segments.

---

### 5. Who Are the Highest-Value Customers?

Top customers typically exhibit:

- Customer Value Scores between 2400–2650
- Customer tenure greater than 4000 days
- High campaign engagement
- Frequent purchasing activity

---

## 📈 Key Visualizations

- Revenue by Age Group
- Campaign Success Rate
- Channel Performance Comparison
- Income vs Spending Analysis
- Top Customer Segments

---

## 💡 Key Insights

- Customers aged 55+ demonstrate the highest spending behavior.
- Campaign 4 achieves the best conversion rate.
- Store purchases generate the highest revenue.
- High-income customers respond more positively to campaigns.
- A small percentage of customers contribute the majority of revenue.

---

## 📌 Business Recommendations

### Customer Targeting

- Focus campaigns on high-value customer segments.
- Personalize offers for premium customers.

### Campaign Optimization

- Improve or redesign underperforming campaigns.
- Reallocate budget toward successful campaigns.

### Channel Strategy

- Strengthen high-performing sales channels.
- Continue investing in store and web experiences.

### Conversion Improvement

- Use customer segmentation to improve targeting.
- Develop tailored marketing strategies for different income groups.

---

## 🚀 Conclusion

This project successfully identified:

- High-value customer segments
- Most effective marketing campaigns
- Best-performing sales channels
- Spending patterns across customer groups

The findings provide actionable recommendations that can help businesses improve marketing ROI, increase customer engagement, and optimize future marketing campaigns.

---

## 📎 Resources

### Dataset

Kaggle Customer Personality Analysis Dataset

https://www.kaggle.com/datasets/rodsaldanha/marketing-campaign

### Dashboard

📄 [View Marketing Campaign Dashboard (PDF)](/marketing_campaign_dashboard.pdf)

## 👤 Author

**Siddhi Kholkar**

Data Analytics Portfolio Project
