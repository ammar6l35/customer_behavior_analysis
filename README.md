# Customer Shopping Behavior Analysis

An end-to-end data analytics project that explores spending patterns, customer segments, product preferences, and subscription behavior using Python, SQL (PostgreSQL), Power BI, and Gamma.

---

## Overview

Retail businesses need to understand who their customers are and what drives purchases. This project analyzes **3,900 customer transactions** to answer key business questions and turn the findings into clear recommendations.

**What this project covers:**
- Loading and exploring the dataset in Python
- Cleaning data and engineering new features
- Running business queries in PostgreSQL
- Building an interactive Power BI dashboard
- Writing a full analysis report
- Creating a presentation with Gamma

---

## Dataset

| Detail | Description |
|---|---|
| Rows | 3,900 transactions |
| Columns | 18 |
| Missing data | 37 values in `Review Rating` |

**Key features**
- **Customer demographics:** Age, Gender, Location, Subscription Status
- **Purchase details:** Item Purchased, Category, Purchase Amount (USD), Season, Size, Color
- **Shopping behavior:** Discount Applied, Promo Code Used, Previous Purchases, Frequency of Purchases, Review Rating, Shipping Type, Payment Method

---

## Tools

| Tool | Purpose |
|---|---|
| **Python** (pandas) | Data loading, EDA, cleaning, feature engineering |
| **PostgreSQL** | Business analysis with SQL (MySQL or SQL Server also work with minor syntax changes) |
| **Power BI** | Interactive dashboard |
| **Gamma** | Presentation (PPT) |
| **GitHub** | Version control and project sharing |

---

## Steps

### 1. Data Loading and EDA (Python)
- Loaded the dataset with `pandas`
- Used `df.info()` and `df.describe()` to understand structure and summary statistics

### 2. Data Cleaning
- Checked for null values and filled missing `Review Rating` values with the **median rating of each product category**
- Renamed columns to **snake_case** for consistency
- Verified that `discount_applied` and `promo_code_used` were redundant, then dropped `promo_code_used`

### 3. Feature Engineering
- `age_group`: customers grouped into age bins
- `purchase_frequency_days`: purchase frequency converted into days

### 4. SQL Analysis
Loaded the cleaned data into PostgreSQL and answered 10 business questions:

1. Revenue by gender
2. High-spending customers who used discounts
3. Top 5 products by average rating
4. Standard vs. Express shipping spend
5. Subscribers vs. non-subscribers
6. Discount-dependent products
7. Customer segmentation (New, Returning, Loyal)
8. Top 3 products per category
9. Repeat buyers and subscriptions
10. Revenue by age group

### 5. Power BI Dashboard
Built an interactive dashboard with KPI cards, charts, and filters (see below).

### 6. Report and Presentation
- Wrote a full analysis report (PDF)
- Created a presentation using Gamma

---

## Dashboard

The Power BI dashboard includes:
- **KPIs:** Number of customers, average purchase amount, average review rating
- **Charts:** Subscription split, revenue and sales by category, revenue and sales by age group
- **Filters:** Subscription status, gender, category, shipping type

![Customer Behavior Dashboard](images/dashboard.png)

---

## Results

**Key insights**
- Male customers generated about **2x the revenue** of female customers ($157,890 vs. $75,191).
- Only **27%** of customers are subscribers, and their average spend ($59.49) is almost the same as non-subscribers ($59.87).
- **3,116** of the customers fall into the **Loyal** segment.
- **Young Adults** contribute the highest revenue of any age group.
- **Hats, sneakers, and coats** are among the most discount-dependent products.
- Express shipping customers spend slightly more on average ($60.48 vs. $58.46).
- **Clothing** is the top category by revenue and sales, followed by Accessories.

**Business recommendations**
- **Boost subscriptions:** promote exclusive subscriber benefits
- **Loyalty programs:** reward repeat buyers to move them into the Loyal segment
- **Review discount policy:** balance sales growth with margin control
- **Product positioning:** highlight top-rated and best-selling products in campaigns
- **Targeted marketing:** focus on high-revenue age groups and express-shipping users

---

## How to Run

**1. Clone the repository**
```bash
git clone https://github.com/your-username/customer-shopping-behavior-analysis.git
cd customer-shopping-behavior-analysis
```

**2. Install the required Python libraries**
```bash
pip install pandas numpy sqlalchemy psycopg2-binary jupyter
```

**3. Run the Python notebook**
```bash
jupyter notebook notebooks/customer_behavior_analysis.ipynb
```
This loads the data, performs EDA and cleaning, and sends the cleaned table to PostgreSQL.

**4. Run the SQL queries**
- Create a PostgreSQL database
- Update the connection details in the notebook (username, password, database name)
- Run the queries in `sql/business_queries.sql`

**5. Open the dashboard**
- Open `dashboard/customer_behavior_dashboard.pbix` in Power BI Desktop
- Refresh the data source if needed

---

## Project Structure

```
customer-shopping-behavior-analysis/
│
├── data/                  # Raw dataset
├── notebooks/             # Python EDA and cleaning
├── sql/                   # SQL business queries
├── dashboard/             # Power BI file
├── images/                # Dashboard screenshots
├── report/                # Analysis report (PDF)
├── presentation/          # Gamma presentation (PPT/PDF)
└── README.md
```

---

## Author

**Your Name**
[LinkedIn](https://linkedin.com/in/your-profile) | [GitHub](https://github.com/your-username) | your.email@example.com
