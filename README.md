# Kultra-Mega-Stores
A complete SQL case study on Kultra Mega Stores (KMS), analyzing sales performance, customer behavior, and operational insights from 2009 to 2012. Includes 11 business questions answered with SQL queries and data-driven recommendations for management.

Kultra Mega Stores - SQL Case Study (2009–2012)

Overview

This case study explores transactional and customer data from Kultra Mega Stores (KMS) using SQL. The goal is to extract business insights from raw data to assist management in making data-informed decisions.

📦 Scenario I – Sales & Operations Analysis

1. Product Category with Highest Sales

SELECT
    Product_Category,
    SUM(Sales) AS Total_Sales
FROM [KMS Sql Case Study]
GROUP BY Product_Category
ORDER BY Total_Sales DESC;

Insight: Office Supplies and Furniture were among the highest contributors to revenue.

2. Top 3 and Bottom 3 Regions by Sales

-- Top 3 Regions
SELECT TOP 3
    Region,
    SUM(Sales) AS Total_Sales
FROM [KMS Sql Case Study]
GROUP BY Region
ORDER BY Total_Sales DESC;

-- Bottom 3 Regions
SELECT TOP 3
    Region,
    SUM(Sales) AS Total_Sales
FROM [KMS Sql Case Study]
GROUP BY Region
ORDER BY Total_Sales ASC;

Insight: Certain regions significantly underperformed and may need targeted marketing strategies.

3. Appliance Sales in Ontario

SELECT
    SUM(Sales) AS Appliance_Sales_Ontario
FROM [KMS Sql Case Study]
WHERE Product_Sub_Category = 'Appliances'
  AND Province = 'Ontario';

Insight: No appliance sales were recorded under Product_Category; the appliances were tracked under Product_Sub_Category.

4. Revenue Boost from Bottom 10 Customers

SELECT TOP 10
    Customer_Name,
    SUM(Sales) AS Total_Sales
FROM [KMS Sql Case Study]
GROUP BY Customer_Name
ORDER BY Total_Sales ASC;

Recommendation: Offer targeted incentives or bundles to encourage repeat purchases.

5. Shipping Method with Highest Cost

SELECT
    Ship_Mode,
    SUM(Shipping_Cost) AS Total_Shipping_Cost
FROM [KMS Sql Case Study]
GROUP BY Ship_Mode
ORDER BY Total_Shipping_Cost DESC;

Insight: Delivery Truck incurred the highest shipping cost.

👥 Scenario II – Customers, Segments & Returns

6. Most Valuable Customers

SELECT TOP 10
    Customer_Name,
    SUM(Sales) AS Total_Sales
FROM [KMS Sql Case Study]
GROUP BY Customer_Name
ORDER BY Total_Sales DESC;

Insight: These customers can be nurtured with loyalty programs.

7. Top Small Business Customer

SELECT TOP 1
    Customer_Name,
    SUM(Sales) AS Total_Sales
FROM [KMS Sql Case Study]
WHERE Customer_Segment = 'Small Business'
GROUP BY Customer_Name
ORDER BY Total_Sales DESC;

8. Most Active Corporate Customer (by orders)

SELECT TOP 1
    Customer_Name,
    COUNT(*) AS Order_Count
FROM [KMS Sql Case Study]
WHERE Customer_Segment = 'Corporate'
GROUP BY Customer_Name
ORDER BY Order_Count DESC;

9. Most Profitable Consumer Customer

SELECT TOP 1
    Customer_Name,
    SUM(Profit) AS Total_Profit
FROM [KMS Sql Case Study]
WHERE Customer_Segment = 'Consumer'
GROUP BY Customer_Name
ORDER BY Total_Profit DESC;

10. Returned Orders and Customer Segments

SELECT DISTINCT
    k.Customer_Name,
    k.Customer_Segment
FROM [KMS Sql Case Study] k
JOIN returns r
    ON k.Order_ID = r.[Order ID];

Insight: Returns were distributed across all customer segments, with some repeat returners.

11. Order Priority vs Shipping Method

SELECT
    Order_Priority,
    Ship_Mode,
    COUNT(*) AS Order_Count
FROM [KMS Sql Case Study]
GROUP BY Order_Priority, Ship_Mode
ORDER BY Order_Priority, Order_Count DESC;

Insight: While high-priority orders often used fast shipping methods, some critical/high orders were still sent via Delivery Truck. Also, 1,672 orders had no specified priority.

🛠 Tools Used

Microsoft SQL Server

Excel (for return data verification)

🧠 Key Takeaways

SQL enables fast and scalable sales insights

Segment-based strategies are essential for marketing and retention

Shipping operations need better alignment with priority levels

Prepared by: [Your Name]Date: [Insert Date]
