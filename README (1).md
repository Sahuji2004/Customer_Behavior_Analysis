# 🛍️ Customer Shopping Behavior Analysis

An end-to-end **data analytics project** that analyzes customer shopping behavior using **Python, PostgreSQL (SQL) and Power BI**. The project works with transactional data from **3,900 purchases** to identify spending patterns, customer segments, product preferences, discount behavior, and subscription trends.

**Workflow:** Raw Data → Python Cleaning & EDA → Feature Engineering → PostgreSQL SQL Analysis → Power BI Dashboard → Business Recommendations

## 🎯 Objectives

- Clean and prepare the customer shopping dataset.
- Handle missing values and improve data consistency.
- Create analytical features such as age groups and purchase frequency.
- Store the cleaned data in PostgreSQL and answer business questions with SQL.
- Build an interactive Power BI dashboard.
- Turn the findings into actionable business recommendations.

## 📊 Dataset Summary

| Attribute | Details |
|---|---|
| Total Records | 3,900 |
| Total Columns | 18 |
| Data Type | Customer transaction / purchase data |
| Missing Values | 37 values in `Review Rating` |

**Customer demographics:** Age, Gender, Location, Subscription Status
**Purchase details:** Item Purchased, Category, Purchase Amount, Season, Size, Color
**Shopping behavior:** Discount Applied, Promo Code Used, Previous Purchases, Frequency of Purchases, Review Rating, Shipping Type

## 🛠️ Technologies Used

- **Python (Pandas):** data cleaning, EDA, feature engineering
- **PostgreSQL:** SQL queries, aggregation, customer segmentation
- **Power BI:** KPI cards, charts, slicers, interactive dashboard

## 🔄 Project Workflow

### 1. Data Loading & Cleaning (Python)
- Loaded the dataset with Pandas and inspected it using `df.info()`, `df.describe()` and null-value checks.
- Imputed missing **Review Rating** values using the **median rating of each product category**.
- Standardized column names to **snake_case**.
- Checked consistency between `discount_applied` and `promo_code_used`, then removed the redundant `promo_code_used` column.

### 2. Feature Engineering
- `age_group`: customer ages grouped into meaningful bands.
- `purchase_frequency_days`: derived from purchase-frequency information.
- Customer segments **New / Returning / Loyal** based on purchase history.

### 3. PostgreSQL Integration
The cleaned DataFrame was loaded into a PostgreSQL table (`customer`) and analyzed with SQL.

## 🔎 SQL Business Analysis

The SQL file answers 10 business questions:

1. **Revenue by Gender**: total revenue from male vs. female customers
2. **High-Spending Discount Users**: customers who used a discount but spent above the average
3. **Top 5 Products by Rating**: highest average review ratings
4. **Shipping Type Comparison**: average purchase amount, Standard vs. Express
5. **Subscribers vs. Non-Subscribers**: average spend and total revenue
6. **Discount-Dependent Products**: top 5 products by share of discounted purchases
7. **Customer Segmentation**: New, Returning and Loyal customers
8. **Top 3 Products per Category**: most purchased products within each category
9. **Repeat Buyers & Subscriptions**: relationship between repeat purchasing (>5 purchases) and subscription
10. **Revenue by Age Group**: revenue contribution of each age group

## 📈 Key Findings

Total revenue in the dataset is **233,081**.

**Revenue by gender**

| Gender | Revenue |
|---|---:|
| Male | 157,890 (about 68%) |
| Female | 75,191 (about 32%) |

**Subscription analysis**

| Subscribed | Customers | Avg. Spend | Total Revenue |
|---|---:|---:|---:|
| Yes | 1,053 | 59.49 | 62,645 |
| No | 2,847 | 59.87 | 170,436 |

Subscribers are about 27% of customers but do **not** spend more per purchase than non-subscribers, so subscription is a growth opportunity rather than a proven spending driver.

**Customer segments**

| Segment | Customers |
|---|---:|
| Loyal | 3,116 (80%) |
| Returning | 701 |
| New | 83 |

**Shipping type**

| Shipping Type | Avg. Purchase Amount |
|---|---:|
| Express | 60.48 |
| Standard | 58.46 |

**Top 5 products by average rating**

| Product | Avg. Rating |
|---|---:|
| Gloves | 3.86 |
| Sandals | 3.84 |
| Boots | 3.82 |
| Hat | 3.80 |
| Skirt | 3.78 |

**Products with the highest discount dependence**

| Product | Discounted Purchases (%) |
|---|---:|
| Hat | 50.00 |
| Sneakers | 49.66 |
| Coat | 49.07 |
| Sweater | 48.17 |
| Pants | 47.37 |

**Revenue by age group**

| Age Group | Total Revenue |
|---|---:|
| Young Adult | 62,143 |
| Middle-aged | 59,197 |
| Adult | 55,978 |
| Senior | 55,763 |

## 📊 Power BI Dashboard

The interactive dashboard (`my_first_dash.pbix`) includes:

- Total customers, average purchase amount and average review rating (KPI cards)
- Subscription status distribution
- Revenue and sales by category
- Revenue and sales by age group
- Slicers for subscription status, gender, category and shipping type

<!-- To show a dashboard preview: upload a screenshot to an "images" folder, then remove these comment markers:
![Customer Behavior Dashboard](images/customer-behavior-dashboard.png)
-->

## 💡 Business Recommendations

1. **Boost subscriptions:** offer exclusive benefits and incentives, since subscribers currently spend about the same as non-subscribers.
2. **Reward loyalty:** build loyalty programs for repeat buyers.
3. **Review discount policy:** several products (Hat, Sneakers, Coat) are bought with a discount nearly half the time, so balance sales growth with margin.
4. **Product positioning:** feature highly rated and best-selling products in campaigns.
5. **Targeted marketing:** focus on high-revenue age groups and Express-shipping customers.

## 📁 Repository Contents

| File | Description |
|---|---|
| `custom.ipynb` | Python notebook: data cleaning, EDA, feature engineering, load to PostgreSQL |
| `customer_behavior_sql_queries.sql` | SQL queries for the 10 business questions |
| `my_first_dash.pbix` | Power BI dashboard |
| [`Business Problem  Document.pdf`](Business%20Problem%20%20Document.pdf) | Business problem statement |
| [`Customer Shopping Behavior Analysis.pdf`](Customer%20Shopping%20Behavior%20Analysis.pdf) | Written project report |
| [`customer_shopping_analysis.pdf.f.pdf`](customer_shopping_analysis.pdf.f.pdf) | Findings readout |

## 🚀 How to Run

1. Clone the repository and place the dataset as `customer_shopping_behavior.csv` in the same folder (the CSV is not included in this repo).
2. Install the libraries: `pip install pandas sqlalchemy psycopg2-binary`
3. Open `custom.ipynb`, set your PostgreSQL connection details, and run all cells to clean the data and load it into the database.
4. Run `customer_behavior_sql_queries.sql` in pgAdmin or any PostgreSQL client.
5. Open `my_first_dash.pbix` in Power BI Desktop and refresh the data source if needed.

## 📚 Skills Demonstrated

Data Cleaning · EDA · Feature Engineering · Python / Pandas · SQL / PostgreSQL · Customer Segmentation · Revenue & KPI Analysis · Power BI Dashboard Development · Business Insight Generation

## 👤 Author

**Gaurav Sahu**
B.Tech CSE (Data Science), Greater Noida

[LinkedIn](https://www.linkedin.com/in/gaurav-sahu-767040230/) · [GitHub](https://github.com/Sahuji2004) · sahugaurav8023@gmail.com
