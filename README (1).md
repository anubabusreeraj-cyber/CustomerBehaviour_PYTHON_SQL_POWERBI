# Customer Shopping Behavior Analysis

An end-to-end data analytics project that uses **Python**, **PostgreSQL** and **Power BI** to study customer shopping behavior and turn it into actionable business recommendations.

## Business Problem

A leading retail company has seen buying patterns shift across demographics, product categories and sales channels (online and in-store). Management wants to know which factors, such as discounts, reviews, seasons and payment preferences, drive purchases and repeat buying.

**Key question:** *How can the company use its consumer shopping data to spot trends, strengthen customer engagement, and refine its marketing and product strategies?*

## Dataset

- **3,900** transactions, **18** columns
- **Demographics:** Age, Gender, Location, Subscription Status
- **Purchase details:** Item Purchased, Category, Purchase Amount, Season, Size, Color
- **Shopping behavior:** Discount Applied, Promo Code Used, Previous Purchases, Frequency of Purchases, Review Rating, Shipping Type
- **Missing values:** 37 in Review Rating

## Tech Stack

| Stage | Tool |
|---|---|
| Data cleaning and feature engineering | Python (pandas) |
| Data storage and analysis | PostgreSQL (SQL) |
| Visualization | Power BI |

## Workflow

1. **Data preparation (Python)**
   - Loaded and explored the data (`df.info()`, `.describe()`)
   - Filled missing review ratings with the median rating for each product category
   - Renamed columns to `snake_case`
   - Created `age_group` and `purchase_frequency_days` features
   - Dropped `promo_code_used` because it duplicated `discount_applied`
   - Loaded the cleaned data into PostgreSQL

2. **SQL analysis (PostgreSQL)** answered 10 business questions:
   - Revenue by gender
   - Discount users who still spend above average
   - Top 5 products by average rating
   - Standard vs. Express shipping spend
   - Subscribers vs. non-subscribers
   - Products most dependent on discounts
   - Customer segmentation (New / Returning / Loyal)
   - Top 3 products per category
   - Whether repeat buyers (more than 5 purchases) are more likely to subscribe
   - Revenue by age group

3. **Dashboard (Power BI):** an interactive dashboard showing customer count, average purchase amount, average rating, and breakdowns by category, subscription, age group and shipping type.

## Key Insights

- Male customers generated about twice the revenue of female customers ($157,890 vs. $75,191).
- Express shipping orders have a slightly higher average value than Standard ($60.48 vs. $58.46).
- Most customers fall into the **Loyal** segment (3,116), compared with 701 Returning and 83 New.
- Most repeat buyers are **not** subscribers (2,518 vs. 958), which shows room to grow subscriptions.
- Young Adults bring in the most revenue ($62,143), and Seniors the least ($55,763).
- Hats, Sneakers and Coats have the highest discount rates (about 49–50%).

## Business Recommendations

- **Grow subscriptions:** promote exclusive benefits for subscribers.
- **Loyalty programs:** reward repeat buyers to move them into the Loyal segment.
- **Review the discount policy:** balance the sales boost against margins.
- **Product positioning:** feature top-rated and best-selling products in campaigns.
- **Targeted marketing:** focus on high-revenue age groups and express-shipping customers.

## Repository Structure

```
├── data/          # Raw and cleaned dataset
├── notebooks/     # Python data cleaning and EDA
├── sql/           # PostgreSQL analysis queries
├── dashboard/     # Power BI (.pbix) file
├── reports/       # Project report and presentation
└── README.md
```

## How to Run

1. Clone the repository.
2. Run the Python notebook in `notebooks/` to clean the data and load it into PostgreSQL. Update the database connection details first.
3. Run the queries in `sql/` against the loaded table.
4. Open the `.pbix` file in `dashboard/` with Power BI Desktop.
