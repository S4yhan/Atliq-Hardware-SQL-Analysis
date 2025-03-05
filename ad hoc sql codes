1. Provide the list of markets in which customer "Atliq Exclusive" operates its business in the APAC region

SELECT
	DISTINCT market
FROM
    dim_customer
WHERE
    customer = "Atliq Exclusive" AND region = "APAC";

---------------------------------------------------------------------------------------------------------------------------------------
2. What is the percentage of unique product increase in 2021 vs. 2020? The final output contains these fields,
-- unique_products_2020
-- unique_products_2021
-- percentage_chg

SELECT   
	table_2020.unique_product_2020 AS unique_products_2020,
    table_2021.unique_product_2021 AS unique_products_2021,
    ((table_2021.unique_product_2021-table_2020.unique_product_2020)/table_2020.unique_product_2020)*100 AS percentage_chg
FROM
		( SELECT COUNT(DISTINCT product_code) AS unique_product_2020 FROM fact_gross_price WHERE fiscal_year = 2020 ) AS table_2020,
		( SELECT COUNT(DISTINCT product_code) AS unique_product_2021 FROM fact_gross_price WHERE fiscal_year = 2021 ) AS table_2021 ;

---------------------------------------------------------------------------------------------------------------------------------------
3. Provide a report with all the unique product counts for each segment and sort them in descending order of product counts. The final output
-- segment
-- product_count

SELECT
	segment,
    COUNT(DISTINCT product_code) AS product_count
FROM
    dim_product
GROUP BY segment
ORDER BY product_count DESC;

---------------------------------------------------------------------------------------------------------------------------------------
 4. Follow-up: Which segment had the most increase in unique products in 2021 vs 2020? The final output contains these fields,
-- segment
-- product_count_2020
-- product_count_2021
-- difference

SELECT
	segment,
    SUM(CASE WHEN fiscal_year=2020 THEN 1 ELSE 0 END) AS product_count_2020,
    SUM(CASE WHEN fiscal_year=2021 THEN 1 ELSE 0 END) AS product_count_2021,
	(SUM(CASE WHEN fiscal_year=2021 THEN 1 ELSE 0 END)- SUM(CASE WHEN fiscal_year=2020 THEN 1 ELSE 0 END)) AS difference
FROM
    dim_product
JOIN fact_gross_price
USING (product_code)
GROUP BY segment
ORDER BY difference DESC;

---------------------------------------------------------------------------------------------------------------------------------------
5 Get the products that have the highest and lowest manufacturing costs.The final output should contain these fields,
-- product_code
-- product
-- manufacturing_cost

SELECT
	product_code, product, manufacturing_cost
FROM
	fact_manufacturing_cost
JOIN dim_product
USING (product_code)
WHERE manufacturing_cost=(SELECT MAX(manufacturing_cost) FROM fact_manufacturing_cost)
UNION ALL
SELECT
	product_code, product, manufacturing_cost
FROM
	fact_manufacturing_cost
JOIN dim_product
USING (product_code)
WHERE manufacturing_cost=(SELECT MIN(manufacturing_cost) FROM fact_manufacturing_cost);

---------------------------------------------------------------------------------------------------------------------------------------
6. Generate a report which contains the top 5 customers who received an average high pre_invoice_discount_pct for the fiscal year 2021 and in the Indian market.
-- customer_code
-- customer
-- average_discount_percentage

SELECT
	d.customer_code, d.customer,
    ROUND(AVG(f.pre_invoice_discount_pct),4) AS average_discount_percentage
FROM
    dim_customer d
JOIN
    fact_pre_invoice_deductions f
USING (customer_code)
WHERE f.fiscal_year=2021 AND d.market='india'
GROUP BY d.customer, d.customer_code
ORDER BY average_discount_percentage DESC
LIMIT 5;

---------------------------------------------------------------------------------------------------------------------------------------
7. Get the complete report of the Gross sales amount for the customer “Atliq Exclusive” for each month. This analysis helps to get an idea of low and high-performing months and take strategic decisions.
The final report contains these columns:
-- Month
-- Year
-- Gross sales Amount

SELECT
    fs.fiscal_year AS Fiscal_Year,
    MONTH(fs.date) AS Month,
    ROUND(SUM(fs.sold_quantity * fp.gross_price), 2) AS Gross_sales_amount
FROM fact_sales_monthly fs
JOIN dim_customer dc
    ON fs.customer_code = dc.customer_code
JOIN fact_gross_price fp
    ON fs.product_code = fp.product_code
WHERE dc.customer = 'Atliq Exclusive'
GROUP BY Month, Fiscal_year
ORDER BY Fiscal_year;

---------------------------------------------------------------------------------------------------------------------------------------
8. In which quarter of 2020, got the maximum total_sold_quantity? The final output contains these fields sorted by the 
-- total_sold_quantity,
-- Quarter
-- total_sold_quantity

# Using fiscal_year
SELECT
	CASE
		WHEN MONTH(date) BETWEEN 9 AND 11 THEN 'Q1'
        WHEN MONTH(date) IN (12,1,2) THEN 'Q2'
        WHEN MONTH(date) BETWEEN 3 AND 5 THEN 'Q3'
        ELSE 'Q4'
    END AS quarter,
    ROUND(SUM(sold_quantity)/1000000,2) AS total_sold_quantity
FROM fact_sales_monthly
WHERE fiscal_year=2020
GROUP BY quarter
ORDER BY total_sold_quantity DESC;

---------------------------------------------------------------------------------------------------------------------------------------
9. Which channel helped to bring more gross sales in the fiscal year 2021 and the percentage of contribution? The final output contains these fields,
-- channel
-- gross_sales_mln
-- percentage

WITH gross_sales_table AS(SELECT
	channel,
    SUM(fgp.gross_price * fsm.sold_quantity) AS gross_sales
FROM fact_sales_monthly fsm
JOIN dim_customer dc
USING (customer_code)
JOIN fact_gross_price fgp
USING (product_code)
WHERE fsm.fiscal_year=2021
GROUP BY dc.channel
ORDER BY gross_sales DESC)
SELECT
	channel,
    ROUND((gross_sales/1000000),2) AS gross_sales_mln,
    ROUND((gross_sales/(SUM(gross_sales) OVER()))*100,2) AS percentage
FROM
	gross_sales_table;

---------------------------------------------------------------------------------------------------------------------------------------
10. Get the Top 3 products in each division that have a hightotal_sold_quantity in the fiscal_year 2021? The final output contains fields,
-- division
-- product_code
-- product
-- total_sold_quantity
-- rank_order

WITH total_sales AS (
SELECT
    dp.product,
    dp.product_code,
    dp.division,
    SUM(fsm.sold_quantity) AS total_sold_quantity,
    RANK() OVER(PARTITION BY division ORDER BY SUM(fsm.sold_quantity) DESC) AS rank_order
FROM fact_sales_monthly fsm
JOIN dim_product dp
    USING (product_code)
WHERE fiscal_year = 2021
GROUP BY dp.product_code, dp.product, dp.division
)
SELECT *
FROM total_sales
WHERE rank_order IN (1,2,3);
