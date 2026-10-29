# Customer Shopping Behavior Analysis

End-to-end analysis of customer shopping behavior using **Python, PostgreSQL, and Power BI**. The project covers 3,900 retail transactions and turns raw data into business insights and recommendations on customer segmentation, subscriptions, discounts, and revenue drivers.

## Business Problem

A retail company wants to understand how its customers shop in order to improve sales, customer satisfaction, and long-term loyalty. Management has noticed changing purchase patterns across demographics, product categories, and sales channels, and wants to know which factors (discounts, reviews, seasons, payment preferences) drive purchases and repeat buying.

> **Key question:** How can the company use consumer shopping data to identify trends, improve customer engagement, and optimize marketing and product strategies?

## Tools and Skills

| Area | Tools / Techniques |
|------|--------------------|
| Data preparation | Python, pandas, Jupyter Notebook |
| Database and analysis | PostgreSQL, CTEs, window functions, subqueries, CASE statements |
| Visualization | Power BI (KPI cards, slicers, interactive charts) |
| Reporting | Written report and stakeholder presentation |

## Dataset

- **Rows:** 3,900 transactions
- **Columns:** 18
- **Customer demographics:** age, gender, location, subscription status
- **Purchase details:** item purchased, category, purchase amount (USD), season, size, color
- **Shopping behavior:** discount applied, promo code used, previous purchases, frequency of purchases, review rating, shipping type, payment method
- **Data quality:** 37 missing values in the review rating column

## Project Workflow

### 1. Data preparation (Python)
- Loaded and explored the dataset with pandas (`info()`, `describe()`)
- Imputed 37 missing review ratings using the median rating of each product category
- Standardized column names to snake case
- Engineered new features: `age_group` (age bins) and `purchase_frequency_days`
- Checked `discount_applied` against `promo_code_used`, found them redundant, and dropped `promo_code_used`
- Loaded the cleaned DataFrame into PostgreSQL for analysis

### 2. Data analysis (PostgreSQL)
Ten business questions answered with SQL:

1. Revenue by gender
2. Discount users who still spent above the average purchase amount
3. Top 5 products by average review rating
4. Average purchase amount: Standard vs. Express shipping
5. Subscribers vs. non-subscribers (customers, average spend, total revenue)
6. Top 5 products with the highest share of discounted purchases
7. Customer segmentation into New, Returning, and Loyal
8. Top 3 most purchased products within each category
9. Subscription status of repeat buyers (more than 5 previous purchases)
10. Revenue contribution by age group

### 3. Dashboard (Power BI)
An interactive dashboard with KPI cards (number of customers, average purchase amount, average review rating), subscription split, revenue and sales by category, and revenue and sales by age group. Slicers let users filter by subscription status, gender, category, and shipping type.

<img width="1310" height="717" alt="Customer_Behavior_Dashboard SS" src="https://github.com/user-attachments/assets/ac92deef-9289-4d72-a840-1807364b95b9" />

![Customer Behavior Dashboard](images/dashboard.png)
-->

## Key Findings

- **Overall:** 3,900 customers, an average purchase amount of $59.76, and an average review rating of 3.75.
- **Subscriptions:** Only 27% of customers (1,053) are subscribers. Non-subscribers generated about $170K of the roughly $233K total revenue, and average spend is nearly the same for both groups ($59.49 for subscribers vs. $59.87 for non-subscribers). Subscribing does not currently translate into higher spend.
- **Gender:** Male customers generated about $157.9K in revenue vs. about $75.2K for female customers.
- **Customer segments:** 3,116 customers are Loyal, 701 are Returning, and 83 are New, so the customer base is dominated by repeat shoppers.
- **Repeat buyers:** Among customers with more than 5 previous purchases, 958 are subscribers and 2,518 are not, so many loyal customers are still unsubscribed.
- **Age groups:** Young Adults contribute the most revenue ($62.1K), followed by Middle-aged ($59.2K), Adult ($56.0K), and Senior ($55.8K). The spread is fairly small.
- **Shipping:** Express shipping customers spend slightly more on average than Standard ($60.48 vs. $58.46).
- **Highest rated products:** Gloves (3.86), Sandals (3.84), Boots (3.82), Hat (3.80), and Skirt (3.78).
- **Most discount-dependent products:** Hat (50.0%), Sneakers (49.7%), Coat (49.1%), Sweater (48.2%), and Pants (47.4%) have the highest share of discounted purchases.
- **Discounts:** 839 purchases used a discount and still exceeded the average purchase amount.
- **Categories:** Clothing is the top category by revenue and sales, followed by Accessories, Footwear, and Outerwear.

## Business Recommendations

- **Boost subscriptions:** Promote exclusive benefits for subscribers, since only 27% of customers subscribe and subscribers do not yet spend more.
- **Loyalty programs:** Reward repeat buyers to keep them in the Loyal segment and convert unsubscribed loyal customers.
- **Review discount policy:** Balance the sales lift from discounts against margin, especially for heavily discounted products like hats and sneakers.
- **Product positioning:** Highlight top-rated and best-selling products in campaigns.
- **Targeted marketing:** Focus on high-revenue age groups and express-shipping users.

## Repository Structure

```
├── customer_behavior_analysis.ipynb        # Python data cleaning and feature engineering
├── customer_behavior_sql_queries.sql       # PostgreSQL analysis queries
├── customer_behavior_dashboard.pbix        # Power BI dashboard
├── customer_shopping_behavior.csv          # Dataset
├── Business_Problem__Document.pdf          # Business problem statement
├── Customer_Shopping_Behavior_Analysis.pdf # Project report
├── Customer-Shopping-Behavior-Analysis.pptx # Presentation
└── README.md
```

## How to Reproduce

1. Open `customer_behavior_analysis.ipynb` in Jupyter and run it to clean the data. Update the PostgreSQL connection details in the notebook to match your own database.
2. Run the queries in `customer_behavior_sql_queries.sql` against the `customer` table in PostgreSQL.
3. Open `customer_behavior_dashboard.pbix` in Power BI Desktop to explore the dashboard.

## Author

**Ammar Ali Khan**
GitHub: [ammar6l35](https://github.com/ammar6l35)
