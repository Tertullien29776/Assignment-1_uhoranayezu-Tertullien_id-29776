# Assignment 1: PL/SQL - Joins, CTEs, and Window Functions

Student Details
Name:Uhoranayezu Tertullien
Student ID:29776
Course: PL/SQL Assignment One
Instructor:Eric Maniraguha 
* **DBMS Used:** Oracle Database (or PostgreSQL / SQL Server)

---

## Business Scenario Summary
**Sunrise Supermarket** manages customer sales, product catalogs, and transaction records. Management requires visibility into customer purchasing behaviors, high-value spenders, and cumulative revenue tracking over time to optimize marketing and inventory strategies.

---

## Summary of Implementation & Queries
This project implements relational database tables (`customers`, `products`, `orders`, `order_items`), populates them with realistic operational data, and extracts analytics using:
1. **Inner Joins:** Matches orders with corresponding customer profile data[cite: 1].
2. **Left Joins:** Identifies all customers, including those who have not yet placed an order[cite: 1].
3. **Common Table Expressions (CTEs):** Computes aggregate customer totals and filters results against the average customer spend[cite: 1].
4. **Window Functions (`RANK`, `ROW_NUMBER`, `LAG`, and cumulative aggregates):** Performs advanced analytical processing such as customer tier ranking, chronological order sequencing, running revenue totals, and purchase frequency intervals[cite: 1].

---

## How to Run
1. Clone or download this repository[cite: 1].
2. Open your preferred SQL/DBMS tool (e.g., Oracle SQL Developer, PostgreSQL pgAdmin)[cite: 1].
3. Execute the script file `schema_and_queries.sql` sequentially to create tables, populate sample rows, and execute the analytical queries.

---

## Business Interpretation
* **Sales Trends:** The running total queries help management monitor daily revenue milestones.
* **Customer Retention:** Tracking the days elapsed between sequential orders via `LAG()` highlights customer purchasing habits and helps identify churn risks.
* **High-Value Segmentation:** CTE and ranking filters spotlight key revenue drivers, enabling targeted loyalty rewards.

---

## Challenges and Resolutions
* **Challenge:** Handling date formatting across different SQL dialects.
  * **Resolution:** Used standard `TO_DATE` functions to ensure uniform data insertion across date attributes.
* **Challenge:** Managing window function frame clauses for running sums.
  * **Resolution:** Grouped transactions by day first using a CTE before applying the cumulative window aggregate.
