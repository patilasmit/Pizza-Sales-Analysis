# Project Title: Pizza Sales Analysis

# Project Overview:  
This project analyzes sales data from a fictional pizza restaurant chain to uncover trends, insights, and business performance metrics. The dataset includes information on customer orders, pizza types, sales prices, and order dates.

**Objectives**:
1. **Data Exploration**: Understand the dataset structure, including tables for orders, pizzas, and customer information.
2. **Data Cleaning**: Handle missing values, remove outliers, and ensure data consistency and integrity.
3. **Sales Analysis**:
   - Calculate **total revenue** over time.
   - Identify the **best-selling pizzas**.
   - Analyze **sales trends** (daily, weekly, monthly).
   - **Segment customers** based on their ordering behavior (frequency and spending).
   - Explore correlations between **pizza toppings** and sales performance.

**Key Analysis Tasks**:
1. **Total Revenue Calculation**: Calculate total sales revenue over a specific time period.
2. **Popular Pizzas**: Identify the most ordered and highest-grossing pizzas.
3. **Sales Trends**: Analyze daily, weekly, and monthly sales trends.
4. **Customer Segmentation**: Segment customers based on their total spending and frequency of orders.
5. **Topping Correlations**: Investigate if certain toppings drive higher sales volumes.

**SQL Skills Demonstrated**:
- Advanced data querying using `SELECT`, `FROM`, `WHERE`, `GROUP BY`, `JOIN`, and `ORDER BY`.
- Aggregation functions: `SUM()`, `COUNT()`, `AVG()`, etc.
- Complex SQL techniques: Subqueries, nested queries, and `HAVING` clauses.
- **Date-based functions** for time series analysis (e.g., `DATEPART`, `YEAR`, `MONTH`).
- **Data Cleaning** techniques (e.g., removing duplicates, handling nulls).

**Tools Used**:
- **Database**: MySQL (RDBMS)
- **IDE**: MySQL Workbench, pgAdmin

**Dataset**:
- **Source**: Simulated pizza sales dataset created for educational purposes.
- **Structure**: Multiple tables, including `Orders`, `Order_Details`, `Pizzas`, and `Pizza_Types`.

**Key Queries**:
1. **Total Revenue Calculation**:
   ```sql
   SELECT SUM(order_amount) AS total_revenue
   FROM orders;
   ```
2. **Best-Selling Pizzas**:
   ```sql
   SELECT pizza_name, COUNT(order_id) AS total_orders
   FROM order_details
   GROUP BY pizza_name
   ORDER BY total_orders DESC;
   ```
3. **Top-Spending Customers**:
   ```sql
   SELECT customer_name, SUM(order_amount) AS total_spent
   FROM orders
   GROUP BY customer_name
   ORDER BY total_spent DESC;
   ```
4. **Sales Trends Over Time**:
   SELECT order_date, SUM(order_amount) AS daily_sales
   FROM orders
   WHERE order_date >= CURDATE() - INTERVAL 30 DAY
   GROUP BY order_date
   ORDER BY order_date ASC;

5. **Order Distribution by Time of Day**:

   SELECT HOUR(order_time) AS hour_of_day, COUNT(order_id) AS total_orders
   FROM orders
   GROUP BY hour_of_day
   ORDER BY total_orders DESC;


**Conclusion**:  
This project demonstrates proficiency in SQL for data manipulation and analysis. It showcases the ability to generate valuable insights from a relational database by analyzing customer behavior, identifying popular products, and exploring sales patterns. The skills applied are highly relevant for business intelligence and data-driven decision-making.
