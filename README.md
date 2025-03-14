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

## Recommendations & Strategic Actions Based on Data Analysis

This data analysis project has yielded key insights into Atliq Hardware's business, providing a data-driven foundation for strategic decision-making.  Based on these findings, we recommend the following actionable steps for Atliq Hardware management to consider:

**1. Leverage APAC Market Strength:**

*   Capitalize on Atliq Exclusive's strong presence in APAC markets.
*   Develop and implement targeted marketing and distribution strategies specifically tailored to key APAC markets identified in the analysis.

**2. Product Portfolio Optimization:**

*   **Prioritize Accessories Segment:**  Invest strategically in the Accessories segment, recognizing its high product portfolio expansion rate.
*   **Sustain Growth in Peripherals & Notebooks:** Continue to support and nurture growth in the Peripherals and Notebook segments.
*   **Re-evaluate Networking Strategy:**  Conduct a review of the Networking segment to revitalize product offerings or adjust the market approach to address its lower product expansion.

**3. Optimize Sales Channel Strategy:**

*   **Strengthen Retail Channel Partnerships:** Reinforce relationships with Retail partners, recognizing Retailers as the dominant gross sales channel.
*   **Enhance Distributor Channel Performance:** Explore strategies to improve the performance of the Distributor channel.
*   **Evaluate Direct Channel Potential:**  Assess the role and future potential of the Direct sales channel to determine if and how its contribution can be increased.

**4. Strategic Discount Management in India:**

*   **Review India Discount Programs:** Critically review current discount strategies for top customers in the Indian market, particularly major e-commerce and retail players.
*   **Optimize for Profitability & Retention:** Ensure that discount programs are strategically optimized to balance profitability and customer retention effectively.

**5. Capitalize on Sales Seasonality:**

*   **Leverage Monthly Sales Patterns:** Utilize the consistent monthly sales patterns and the November peak identified for Atliq Exclusive in targeted marketing campaigns.
*   **Optimize Inventory & Promotions:** Implement proactive inventory management and promotional activities around peak sales periods, particularly in preparation for Q1, identified as the peak sales quarter based on 2020 data.

**6. Product Focus within Divisions:**

*   **Build on Division Leaders:**  Recognize Pen Drives (N&S Division) and Mice (P&A Division) as volume leaders. Consider product development and marketing strategies that further build upon these product category strengths.
*   **Address PC Division Sales Volume:** Analyze the reasons for the PC division's comparatively lower sales volume and develop strategies to boost sales performance in this segment.

These insights provide a data-driven foundation for Atliq Hardwares' management to make informed strategic decisions related to market focus, product portfolio optimization, sales strategies, and customer relationship management.
Video Presentation: https://www.youtube.com/watch?v=j8cE74z-VXQ
