# SQL Business Analysis – DVD Rental Company

## Project Overview

This project presents a business-oriented analysis of a DVD rental company's operational and financial performance using **PostgreSQL** and the **Sakila DVD Rental database**.

The analysis focuses on revenue generation, customer behavior, movie performance, category performance, customer segmentation, ranking, cumulative revenue, and advanced SQL techniques.

The objective is to demonstrate the practical use of SQL to answer business questions and generate actionable insights from relational data.

---

## Business Objectives

The analysis addresses the following business questions:

### Revenue Analysis

1. What is the company's total revenue?
2. What is the average payment amount?
3. How has revenue evolved every month?

### Customer Analysis

4. Who are the Top 10 customers by total spending?
5. Which customers have made the highest number of rentals?
6. Which customers have spent more than the average customer?
7. What is the average amount spent per customer?

### Movie Analysis

8. Which movies are rented most frequently?
9. Which movies generate the highest revenue?
10. Which movies have rental prices above the average rental price?
11. Which movies are longer than the average movie length?

### Category Analysis

12. Which movie categories generate the highest revenue?
13. Which categories have the highest number of rentals?

### Business Insights & Advanced SQL

14. Classify customers into Gold, Silver, and Bronze segments based on total spending.
15. Rank customers by total spending using `RANK()` and `DENSE_RANK()`.
16. Calculate cumulative monthly revenue using a window function.
17. Create a VIP Customers View containing customers whose total spending is above the overall average.
18. Use a CTE to identify customers with above-average spending.
19. Analyze revenue by quarter using date functions and window functions.
20. Evaluate the execution plan of a complex query using `EXPLAIN ANALYZE`.

---

## Dataset

The project uses the **Sakila PostgreSQL sample database**, a relational database representing a fictional DVD rental business.

The database contains information about:

- Customers
- Films
- Categories
- Inventory
- Rentals
- Payments
- Stores
- Staff
- Actors

The analysis primarily uses the following tables:

`customer` · `payment` · `rental` · `film` · `inventory` · `category` · `film_category`

---

## Tools & Technologies

- **PostgreSQL**
- **SQL**
- **DBeaver**
- **GitHub**
- **Sakila DVD Rental Database**

---

## SQL Techniques Used

The project demonstrates a range of SQL techniques, including:

- `SELECT`
- `WHERE`
- `JOIN`
- `GROUP BY`
- `HAVING`
- `ORDER BY`
- `LIMIT`
- Aggregate functions such as `SUM()`, `AVG()`, and `COUNT()`
- Subqueries
- `CASE WHEN`
- Date functions such as `DATE_TRUNC()`
- `EXTRACT()`
- Window functions
- `RANK()`
- `DENSE_RANK()`
- `SUM() OVER()`
- Common Table Expressions (`CTE`)
- SQL Views
- `EXPLAIN ANALYZE`

---

## Key Business Insights

The analysis produced several relevant business findings.

### Customer Value

- **Eleanor Hunt** is the highest-value customer, with total spending of **$211.55**.
- VIP customers, defined as customers whose total spending is above the average customer spending, account for **57.22% of total revenue**.

This indicates that high-value customers account for a substantial share of the company's revenue and may therefore be important to customer retention strategies.

### Movie Performance

- **Telegraph Voyage** generates the highest revenue among individual movies, with **$215.75**.

This is an example of identifying which individual products contribute most strongly to overall revenue.

### Category Performance

- **Sports** is the highest-revenue movie category, generating **$4,892.19**.
- **Sports** is also the most frequently rented category, with **1,179 rentals**.

This category ranking first in both revenue and rental volume indicates strong customer demand for it.

### Revenue Performance

- **April 2007** recorded the highest monthly revenue, reaching **$28,559.46**.
- Monthly and quarterly revenue analysis was performed using `DATE_TRUNC()`, `EXTRACT()`, and SQL window functions.
- Cumulative revenue calculations provide a view of how revenue accumulated over time.

### Customer Segmentation

Customers were segmented according to their total spending:

| Segment | Total Spending |
|---------|----------------|
| Gold | ≥ $150 |
| Silver | $100 – $149.99 |
| Bronze | < $100 |

This segmentation can help management identify high-value customers and prioritize customer retention strategies.

### Query Performance

The execution plan of the quarterly revenue analysis was evaluated using `EXPLAIN ANALYZE`.

The query produced:

- **Planning Time:** 0.179 ms
- **Execution Time:** 10.576 ms

The execution plan included a sequential scan of the `payment` table, sorting by quarter, and a `GroupAggregate` operation.

This demonstrates the use of PostgreSQL query-plan analysis to evaluate how a query is executed by the database engine.

---

## Repository Structure

```text
SQL-dvd-rental-business-analysis/
│
├── sql/
│   └── dvd_rental_business_analysis.sql
│
└── README.md
