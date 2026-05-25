# 👨🏻‍💻 Customer Behavior Analysis using SQL & Python

This project focuses on analyzing customer transaction data using Python and PostgreSQL to uncover meaningful business insights related to customer purchasing behavior, revenue contribution, customer retention, and product performance.

The project demonstrates practical skills in:
- 📊 Exploratory Data Analysis (EDA)
- 🐍 Data Cleaning using Python
- 🗄️ SQL-based Business Analysis using PostgreSQL
- 📈 Customer Segmentation & Revenue Analysis
- 💼 Business Problem Solving using Data

---

# 📌 Project Overview

The objective of this project is to analyze customer transaction records and extract actionable business insights using SQL and Python.

The project workflow includes:

✅ Loading and preprocessing the dataset using Python

✅ Performing Exploratory Data Analysis (EDA)

✅ Cleaning and transforming raw data

✅ Running SQL queries in PostgreSQL

✅ Identifying customer behavior and revenue trends

✅ Generating business insights for decision-making

---

# 🗂️ Dataset Information

The dataset contains:
- Customer details
- Product information
- Purchase amount
- Review ratings
- Shipping type
- Subscription status
- Previous purchases
- Product category information

The dataset was analyzed to understand:
- Revenue contribution
- Customer retention behavior
- Repeat customer analysis
- Product performance
- Discount impact on sales

---

# 🛠️ Tools & Technologies Used

| Tool | Purpose |
|------|---------|
| Python | Data cleaning & analysis |
| PostgreSQL | SQL querying |
| Pandas | Data manipulation |
| NumPy | Numerical operations |
| Jupyter Notebook | Analysis environment |
| SQL | Business analysis |

---

# 🔄 Project Workflow

## 1️⃣ Data Loading
- Imported dataset using Pandas
- Loaded customer transaction data into PostgreSQL

## 2️⃣ Data Cleaning
- Handled missing values
- Removed duplicate records
- Standardized data formats
- Checked data consistency

## 3️⃣ Exploratory Data Analysis (EDA)
Performed analysis on:
- Customer purchasing behavior
- Revenue distribution
- Product performance
- Shipping trends
- Subscription behavior

## 4️⃣ SQL Analysis
Used PostgreSQL queries to analyze:
- Revenue by gender
- Customer spending patterns
- Top-rated products
- Shipping type comparisons
- Subscription-based revenue contribution
- Repeat customer behavior
- Product category performance

### SQL Concepts Used
- GROUP BY
- CASE WHEN
- Aggregate Functions
- Window Functions
- CTEs
- ORDER BY
- Subqueries

---

# 📊 Sample SQL Queries

## Top 5 Products with Highest Average Ratings

```sql
select item_purchased,
round(avg(review_rating::numeric),2) as avg_rating
from customer
group by item_purchased
order by avg_rating desc
limit 5;
```

## Customer Segmentation Analysis

```sql
with customer_type as (
select customer_id,
previous_purchases,
case
	when previous_purchases = 1 then 'new'
	when previous_purchases between 2 and 10 then 'returning'
	else 'loyal'
	end as customer_segment
from customer
)

select customer_segment,
count(*) as no_of_customer
from customer_type
group by customer_segment;
```

---

# 📈 Key Results & Insights

✅ Repeat customers contributed significantly higher revenue

✅ Identified top-performing products based on customer ratings

✅ Analyzed customer subscription behavior and spending patterns

✅ Found customer segments such as New, Returning, and Loyal customers

✅ Evaluated the impact of discounts on purchasing behavior

✅ Compared revenue trends across shipping methods and customer groups

---

# ▶️ How to Run the Project

## 1. Clone the Repository

```bash
git clone https://github.com/your-username/customer-behavior-analysis.git
cd customer-behavior-analysis
```

## 2. Install Required Libraries

```bash
pip install pandas numpy matplotlib psycopg2
```

## 3. Open Jupyter Notebook

```bash
jupyter notebook
```

## 4. Configure PostgreSQL
- Create a PostgreSQL database
- Import the dataset into PostgreSQL
- Update database credentials in the notebook

## 5. Run the Analysis
Execute notebook cells step-by-step to:
- Load data
- Clean data
- Perform EDA
- Run SQL queries
- Generate business insights

---

# 🚀 Project Highlights

- End-to-end customer analytics workflow
- SQL + Python integration
- Real-world business analysis
- Customer retention analysis
- Recruiter-friendly portfolio project

---

# 👨‍💻 Author

**Priyanshu Tiwari**  
Data Analytics & SQL Enthusiast
