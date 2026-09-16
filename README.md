<?php
/**
 * Assignment 1: PL/SQL - Joins, CTEs, and Window Functions
 * Project Report / README Page
 */
$student_name = "[Your Full Name]";
$student_id = "[Your Student ID]";
$instructor = "Eric Maniraguha";
$ta = "Afanyu Emmanuel";
$dbms = "Oracle Database (or PostgreSQL / SQL Server)";
?>
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Assignment 1: PL/SQL Report</title>
    <style>
        body { font-family: Arial, sans-serif; line-height: 1.6; margin: 40px; background-color: #f8f9fa; color: #333; }
        .container { max-width: 800px; margin: auto; background: #fff; padding: 40px; border-radius: 8px; box-shadow: 0 4px 8px rgba(0,0,0,0.1); }
        h1 { color: #2c3e50; border-bottom: 2px solid #eaeaea; padding-bottom: 10px; }
        h2 { color: #34495e; margin-top: 30px; border-bottom: 1px solid #eee; padding-bottom: 5px; }
        ul { padding-left: 20px; }
        li { margin-bottom: 8px; }
        .meta-box { background: #f1f8ff; border-left: 4px solid #0366d6; padding: 15px; margin-bottom: 20px; border-radius: 0 4px 4px 0; }
        .meta-box p { margin: 5px 0; }
    </style>
</head>
<body>

<div class="container">
    <h1>Assignment 1: PL/SQL - Joins, CTEs, and Window Functions</h1>

    <div class="meta-box">
        <h2>Student Details</h2>
        <p><strong>Name:</strong> <?php echo htmlspecialchars($student_name); ?></p>
        <p><strong>Student ID:</strong> <?php echo htmlspecialchars($student_id); ?></p>
        <p><strong>Course:</strong> PL/SQL Assignment One</p>
        <p><strong>Instructor:</strong> <?php echo htmlspecialchars($instructor); ?> | <strong>TA:</strong> <?php echo htmlspecialchars($ta); ?></p>
        <p><strong>DBMS Used:</strong> <?php echo htmlspecialchars($dbms); ?></p>
    </div>

    <h2>Business Scenario Summary</h2>
    <p><strong>Sunrise Supermarket</strong> manages customer sales, product catalogs, and transaction records. Management requires visibility into customer purchasing behaviors, high-value spenders, and cumulative revenue tracking over time to optimize marketing and inventory strategies.</p>

    <h2>Summary of Implementation & Queries</h2>
    <p>This project implements relational database tables (<code>customers</code>, <code>products</code>, <code>orders</code>, <code>order_items</code>), populates them with realistic operational data, and extracts analytics using:</p>
    <ul>
        <li><strong>Inner Joins:</strong> Matches orders with corresponding customer profile data.</li>
        <li><strong>Left Joins:</strong> Identifies all customers, including those who have not yet placed an order.</li>
        <li><strong>Common Table Expressions (CTEs):</strong> Computes aggregate customer totals and filters results against the average customer spend.</li>
        <li><strong>Window Functions (<code>RANK</code>, <code>ROW_NUMBER</code>, <code>LAG</code>, and cumulative aggregates):</strong> Performs advanced analytical processing such as customer tier ranking, chronological order sequencing, running revenue totals, and purchase frequency intervals.</li>
    </ul>

    <h2>How to Run</h2>
    <ol>
        <li>Clone or download this repository.</li>
        <li>Open your preferred SQL/DBMS tool (e.g., Oracle SQL Developer, PostgreSQL pgAdmin).</li>
        <li>Execute the script file <code>schema_and_queries.sql</code> sequentially to create tables, populate sample rows, and execute the analytical queries.</li>
    </ol>

    <h2>Business Interpretation</h2>
    <ul>
        <li><strong>Sales Trends:</strong> The running total queries help management monitor daily revenue milestones.</li>
        <li><strong>Customer Retention:</strong> Tracking the days elapsed between sequential orders via <code>LAG()</code> highlights customer purchasing habits and helps identify churn risks.</li>
        <li><strong>High-Value Segmentation:</strong> CTE and ranking filters spotlight key revenue drivers, enabling targeted loyalty rewards.</li>
    </ul>

    <h2>Challenges and Resolutions</h2>
    <ul>
        <li>
            <strong>Challenge:</strong> Handling date formatting across different SQL dialects.<br>
            <strong>Resolution:</strong> Used standard <code>TO_DATE</code> functions to ensure uniform data insertion across date attributes.
        </li>
        <li>
            <strong>Challenge:</strong> Managing window function frame clauses for running sums.<br>
            <strong>Resolution:</strong> Grouped transactions by day first using a CTE before applying the cumulative window aggregate.
        </li>
    </ul>
</div>

</body>
</html>
