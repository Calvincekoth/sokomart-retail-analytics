# sokomart-retail-analytics
End-to-end retail analytics project using PostgreSQL and advanced SQL to analyse customer behaviour, sales performance, product pricing, profitability, and business trends across a simulated Kenyan e-commerce business. Demonstrates CTEs, subqueries, window functions, stored procedures, and database optimisation.
# SokoMart Kenya | Advanced SQL & Retail Business Analytics

**Author:** Calvince Okoth  
**Role:** Data Analyst | Aspiring Data Engineer  
**Technology:** PostgreSQL  
**Project Domain:** Retail & E-commerce Analytics  
**Project Period:** November 2026

---

## Project Overview

SokoMart Kenya is a simulated e-commerce retail business operating across multiple counties in Kenya, selling electronics, groceries, fashion, home appliances and beauty products.

This project focuses on using advanced SQL techniques to transform transactional data into meaningful business intelligence.

The objective is to investigate business performance, understand customer purchasing behaviour, evaluate product performance, analyse profitability and improve database efficiency using PostgreSQL.

Rather than focusing only on writing queries, this project demonstrates how SQL can address practical business questions and support data-driven decision-making.

**The dataset and business records are synthetic and are used for analytical and portfolio demonstration purposes.**

## Business Objectives

The analysis explores several important business areas:

- **Customer Analytics:** Identify high-value customers, customer purchasing patterns and customer segmentation opportunities.
- **Sales Performance:** Evaluate revenue trends, monthly performance and order distribution.
- **Product Analytics:** Identify premium-priced products, best-selling products and products with no recorded orders.
- **Profitability Analysis:** Calculate product costs, gross profit and profit margins.
- **Regional Performance:** Compare customer behaviour and sales performance across Kenyan counties.
- **Payment Analytics:** Investigate payment methods, successful transactions and failed payments.
- **Database Engineering:** Develop reusable database objects and improve query performance.

## Technical Stack

| Technology | Application |
|---|---|
| PostgreSQL | Database management and advanced SQL analysis |
| SQL | Data querying and business analytics |
| DBeaver | Database administration and query execution |
| Git & GitHub | Version control and project documentation |
| Excel / Power BI | Potential downstream reporting and visualisation |

## Database Overview

The project uses a relational PostgreSQL database named `luxdevhq_cohort9_advanced_sql`, with the `sokomart` schema.

The dataset contains:

| Table | Records | Description |
|---|---:|---|
| Customers | 5,000 | Customer profiles and locations |
| Products | 300 | Product catalogue and pricing |
| Orders | 50,000 | Customer transactions |
| Order Items | 120,000 | Individual products within orders |
| Payments | 50,000 | Payment transaction records |
| Payment Staging | 2,640 | Raw payment settlement records |

Additional supporting tables are used for database procedures, triggers and price or order-status history.

## Advanced SQL Techniques

This project demonstrates practical application of:

### 1. CTEs and Subqueries
- Common Table Expressions (CTEs)
- Chained CTEs
- Scalar subqueries
- Correlated subqueries
- EXISTS and NOT EXISTS
- Derived tables
- Anti-joins

### 2. Window Functions
- ROW_NUMBER()
- RANK()
- DENSE_RANK()
- LAG() and LEAD()
- NTILE()
- Running totals and moving averages
- Customer and product rankings

### 3. Advanced Aggregation
- GROUP BY and HAVING
- Conditional aggregation
- COUNT(DISTINCT)
- Revenue and profitability analysis
- Multi-level aggregation

### 4. Database Programming
- Creating SQL functions
- Stored procedures
- Input and output parameters
- Exception handling using RAISE EXCEPTION
- Database triggers
- Transaction management

### 5. Database Optimisation
- Index creation
- EXPLAIN ANALYZE
- Query execution plan analysis
- Before-and-after performance comparisons
- COMMIT and ROLLBACK

## Project Structure

```text
sokomart-advanced-sql/
│
├── README.md
│
├── sql/
│   ├── 00_practice_drills.sql
│   ├── section_a_ctes_subqueries.sql
│   ├── section_b_window_functions.sql
│   ├── section_c_advanced_aggregation.sql
│   ├── section_d_database_programming.sql
│   └── section_e_optimisation_transactions.sql
│
├── screenshots/
│   ├── q01_big_spenders_2025.png
│   ├── q02_premium_products.png
│   ├── q03_monthly_profit_loss.png
│   └── ...
│
└── docs/
    └── project_notes.md
```

## Analytical Sections

| Section | Focus | Key Deliverables |
|---|---|---|
| A | CTEs & Subqueries | Customer spending, product pricing and profitability |
| B | Window Functions | Rankings, customer patterns and sales trends |
| C | Advanced Aggregation | Business performance and complex analytical queries |
| D | Database Programming | Views, functions, procedures and triggers |
| E | Optimisation & Transactions | Indexing, query plans and transaction control |

## Key Business Metrics

The following metrics guide the analysis:

- Total completed sales revenue.
- Number of completed orders.
- Average order value.
- Customer lifetime spending within the available dataset.
- Product category performance.
- Cost of goods sold.
- Gross profit.
- Gross profit margin.
- Monthly revenue growth.
- Payment success and failure rates.

**Revenue calculation rule:**

Revenue is calculated using completed orders only:

```sql
SELECT
    SUM(oi.line_total) AS total_revenue
FROM sokomart.order_items oi
JOIN sokomart.orders o
    ON oi.order_id = o.order_id
WHERE o.order_status = 'completed';
```

Delivery fees, cancelled orders, pending orders and returned orders are excluded from revenue.

## Business Insights & Recommendations

The following insights will be populated using actual query results from the project.

1. **Customer Segmentation:** Identify customers with above-average spending and recommend targeted loyalty campaigns.

2. **Product Pricing:** Compare product prices against category averages to identify premium-priced products and review pricing strategies.

3. **Profitability:** Identify categories contributing the highest gross profit and recommend inventory investment based on profitability.

4. **Regional Performance:** Evaluate purchasing activity across counties and identify regions with opportunities for business expansion.

5. **Sales Trends:** Identify high-performing months and recommend inventory planning around seasonal demand.

6. **Product Performance:** Identify products with no recorded orders and recommend reviewing their pricing, visibility and inventory allocation.

7. **Payment Reliability:** Analyse failed payments and recommend improvements to the payment process.

*All numerical findings and final recommendations will be updated from executed SQL results rather than assumed values.*

## Project Execution & Reproducibility

To reproduce the analysis:

**Prerequisites**
- PostgreSQL
- DBeaver or psql
- Git

**Database setup**

1. Download or obtain the SokoMart project dataset.
2. Follow the database setup instructions.
3. Create the database and schema.
4. Create the tables and load the datasets.
5. Execute `06_validation.sql` and confirm that all validation checks return PASS.

**Running the analysis**

Execute the SQL files in sequence:

```text
00_practice_drills.sql
01_section_a_ctes_subqueries.sql
02_section_b_window_functions.sql
03_section_c_advanced_aggregation.sql
04_section_d_database_programming.sql
05_section_e_optimisation_transactions.sql
```

Each section contains documented queries addressing specific business questions.

Screenshots of executed queries and their results are maintained in the `screenshots/` directory.

The original dataset and database dump are not included in this repository.

## What This Project Demonstrates

This project demonstrates my ability to:

- Work with relational databases and structured transactional datasets.
- Translate business requirements into SQL queries.
- Apply advanced PostgreSQL concepts to real-world analytical scenarios.
- Analyse customer behaviour, revenue and product profitability.
- Build reusable database functions and stored procedures.
- Investigate query execution plans and improve database performance.
- Document analytical processes using Git and GitHub.

## About the Author

I am Calvince Okoth, a data analytics professional developing my expertise in data engineering.

My analytics foundation was developed through DataBreed Africa, where I gained practical exposure to data analysis, data cleaning, Excel, SQL and Power BI.

I am currently expanding my technical capabilities through hands-on data engineering projects, focusing on PostgreSQL, database design, Linux, Git and advanced SQL.

I believe in learning through practical projects that solve business problems and demonstrate the value of data.

**Connect with me:**

- GitHub: [Calvincekoth](https://github.com/Calvincekoth)
- LinkedIn: [Calvince Okoth](https://www.linkedin.com/in/calvince-okoth-85792b25a/)

---

*Building practical data solutions. Turning data into decisions.*
