<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Assignment 1: PL/SQL - Joins, CTEs, and Window Functions</title>
    <style>
        :root {
            --primary-color: #2c3e50;
            --accent-color: #3498db;
            --bg-color: #f8f9fa;
            --card-bg: #ffffff;
            --text-color: #333333;
            --border-color: #e1e4e8;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            margin: 0;
            padding: 40px 20px;
            background-color: var(--bg-color);
            color: var(--text-color);
        }

        .container {
            max-width: 850px;
            margin: auto;
            background: var(--card-bg);
            padding: 40px;
            border-radius: 12px;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.05);
        }

        h1 {
            color: var(--primary-color);
            border-bottom: 3px solid var(--accent-color);
            padding-bottom: 12px;
            margin-top: 0;
            font-size: 26px;
        }

        h2 {
            color: var(--primary-color);
            border-bottom: 1px solid var(--border-color);
            padding-bottom: 8px;
            margin-top: 35px;
            font-size: 20px;
        }

        p, li {
            color: #4a5568;
        }

        ul, ol {
            padding-left: 20px;
        }

        li {
            margin-bottom: 10px;
        }

        code {
            background-color: #edf2f7;
            padding: 2px 6px;
            border-radius: 4px;
            font-family: 'Courier New', Courier, monospace;
            font-size: 14px;
            color: #d63384;
        }

        .meta-box {
            background: #f1f8ff;
            border-left: 4px solid var(--accent-color);
            padding: 20px;
            margin: 25px 0;
            border-radius: 0 8px 8px 0;
        }

        .meta-box h2 {
            margin-top: 0;
            border-bottom: none;
            padding-bottom: 0;
            color: #0366d6;
        }

        .meta-box p {
            margin: 8px 0;
        }

        .challenge-box {
            background: #fffaf0;
            border-left: 4px solid #dd6b20;
            padding: 15px 20px;
            margin: 15px 0;
            border-radius: 0 8px 8px 0;
        }

        .challenge-box strong {
            color: #c05621;
        }

        hr {
            border: none;
            border-top: 1px solid var(--border-color);
            margin: 30px 0;
        }
    </style>
</head>
<body>

<div class="container">
    <h1>Assignment 1: PL/SQL - Joins, CTEs, and Window Functions</h1>

    <div class="meta-box">
        <h2>Student Details</h2>
        <p><strong>Name:</strong> [Andika Amazina Yawe Hano]</p>
        <p><strong>Student ID:</strong> [Andika Student ID Yawe Hano]</p>
        <p><strong>Course:</strong> PL/SQL Assignment One</p>
        <p><strong>Instructor:</strong> Eric Maniraguha | <strong>TA:</strong> Afanyu Emmanuel[cite: 1]</p>
        <p><strong>DBMS Used:</strong> Oracle Database (or PostgreSQL / SQL Server)[cite: 1]</p>
    </div>

    <h2>Business Scenario Summary</h2>
    <p><strong>Sunrise Supermarket</strong> manages customer sales, product catalogs, and transaction records. Management requires visibility into customer purchasing behaviors, high-value spenders, and cumulative revenue tracking over time to optimize marketing and inventory strategies.</p>

    <hr>

    <h2>Summary of Implementation & Queries</h2>
    <p>This project implements relational database tables (<code>customers</code>, <code>products</code>, <code>orders</code>, <code>order_items</code>), populates them with realistic operational data, and extracts analytics using:</p>
    <ul>
        <li><strong>Inner Joins:</strong> Matches orders with corresponding customer profile data[cite: 1].</li>
        <li><strong>Left Joins:</strong> Identifies all customers, including those who have not yet placed an order[cite: 1].</li>
        <li><strong>Common Table Expressions (CTEs):</strong> Computes aggregate customer totals and filters results against the average customer spend[cite: 1].</li>
        <li><strong>Window Functions (<code>RANK</code>, <code>ROW_NUMBER</code>, <code>LAG</code>, and cumulative aggregates):</strong> Performs advanced analytical processing such as customer tier ranking, chronological order sequencing, running revenue totals, and purchase frequency intervals[cite: 1].</li>
    </ul>

    <hr>

    <h2>How to Run</h2>
    <ol>
        <li>Clone or download this repository[cite: 1].</li>
        <li>Open your preferred SQL/DBMS tool (e.g., Oracle SQL Developer, PostgreSQL pgAdmin)[cite: 1].</li>
        <li>Execute the script file <code>schema_and_queries.sql</code> sequentially to create tables, populate sample rows, and execute the analytical queries.</li>
    </ol>

    <hr>

    <h2>Business Interpretation</h2>
    <ul>
        <li><strong>Sales Trends:</strong> The running total queries help management monitor daily revenue milestones.</li>
        <li><strong>Customer Retention:</strong> Tracking the days elapsed between sequential orders via <code>LAG()</code> highlights customer purchasing habits and helps identify churn risks.</li>
        <li><strong>High-Value Segmentation:</strong> CTE and ranking filters spotlight key revenue drivers, enabling targeted loyalty rewards.</li>
    </ul>

    <hr>

    <h2>Challenges and Resolutions</h2>
    <div class="challenge-box">
        <p><strong>Challenge:</strong> Handling date formatting across different SQL dialects.</p>
        <p><strong>Resolution:</strong> Used standard <code>TO_DATE</code> functions to ensure uniform data insertion across date attributes.</p>
    </div>
    <div class="challenge-box">
        <p><strong>Challenge:</strong> Managing window function frame clauses for running sums.</p>
        <p><strong>Resolution:</strong> Grouped transactions by day first using a CTE before applying the cumulative window aggregate.</p>
    </div>
</div>

</body>
</html>
