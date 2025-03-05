# Atliq Hardware SQL Data Analysis Project

## Problem Statement

Atliq Hardwares, a leading computer hardware producer, recognized a gap in their ability to leverage data for quick and informed decision-making.  Management observed a need for better insights into their operations to drive strategic growth and optimize business performance.  To address this, they sought to enhance their data analytics capabilities and required a series of ad-hoc data requests to be answered to gain immediate insights.

## Task

The primary task was to act as a junior data analyst and respond to 10 specific business questions provided by Atliq Hardwares' management. This involved:

1.  Analyzing 10 ad-hoc business requests from the consumer goods domain.
2.  Developing and executing SQL queries to retrieve the necessary data and answer each request.
3.  Preparing a presentation to communicate the findings and insights to top-level management.

## Action

To address the tasks, I undertook the following actions:

*   **Data Exploration and Understanding:**  Familiarized myself with the provided Atliq Hardware dataset, including table schemas, relationships, and data dictionaries to understand the available information.
*   **SQL Query Development:** For each of the 10 business requests, I designed and implemented SQL queries using various techniques including:
    *   `SELECT` statements for data retrieval and filtering.
    *   `DISTINCT` to identify unique values.
    *   Aggregate functions (`COUNT`, `SUM`, `AVG`, `MIN`, `MAX`) for data summarization.
    *   `GROUP BY` and `ORDER BY` clauses for data aggregation and sorting.
    *   `JOIN` clauses (`JOIN`, `USING`, `ON`) to combine data from multiple tables (`dim_customer`, `fact_sales_monthly`, `fact_gross_price`, `fact_manufacturing_cost`, `fact_pre_invoice_deductions`, `dim_product`).
    *   Subqueries and Common Table Expressions (CTEs) for complex calculations and data manipulation.
    *   Window functions (`RANK`, `OVER`, `PARTITION BY`) for ranking and comparative analysis.
    *   `CASE` statements for conditional logic and data categorization.
    *   Date functions (`MONTH`, `YEAR`, `MONTHNAME`) for time-based analysis.
    *   Set operations (`UNION ALL`) to combine results from multiple queries.
*   **Data Analysis and Interpretation:** Analyzed the results of the SQL queries to extract meaningful insights relevant to each business question.
*   **Presentation Preparation:**  Prepared a structured output of the SQL queries, ready for presentation to management

## Result

The SQL queries successfully addressed all 10 ad-hoc business requests, providing insights into areas such as:

*   **Market Operations:** Identified specific markets within the APAC region where "Atliq Exclusive" operates.
*   **Product Performance:** Calculated the percentage increase in unique products, identified top and bottom performing products, and analyzed product counts by segment.
*   **Sales Trends:**  Generated monthly gross sales reports for "Atliq Exclusive" and determined the quarter with the highest sales quantity in 2020.
*   **Channel Effectiveness:** Identified the most effective sales channel in 2021 and its contribution to gross sales.
*   **Customer Discount Analysis:**  Reported the top 5 customers receiving the highest average discounts in the Indian market.
*   **Manufacturing Costs:**  Identified products with the highest and lowest manufacturing costs.

These insights provide a data-driven foundation for Atliq Hardwares' management to make informed strategic decisions related to market focus, product portfolio optimization, sales strategies, and customer relationship management.
