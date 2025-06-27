# Kultra-Mega-Stores
A complete SQL case study on Kultra Mega Stores (KMS), analyzing sales performance, customer behavior, and operational insights from 2009 to 2012. Includes 11 business questions answered with SQL queries and data-driven recommendations for management.

Kultra Mega Stores - SQL Case Study (2009–2012)

Overview

This case study explores transactional and customer data from Kultra Mega Stores (KMS) using SQL. The goal is to extract business insights from raw data to assist management in making data-informed decisions.

📦 Scenario I – Sales & Operations Analysis
________________________________________
1. Product Category with Highest Sales

    
       SELECT TOP 1
        Product_Category, 
        SUM(Sales) AS Total_Sales
        FROM [KMS Sql Case Study]
        GROUP BY Product_Category
        ORDER BY Total_Sales DESC;


________________________________________
2. Top 3 and Bottom 3 Regions by Sales
   
-- Top 3 Regions

        SELECT TOP 3 Region,
        SUM(Sales) AS Total_Sales
        FROM [KMS Sql Case Study]
        GROUP BY Region
        ORDER BY Total_Sales DESC;

-- Bottom 3 Regions

        SELECT TOP 3 Region,
        SUM(Sales) AS Total_Sales
        FROM [KMS Sql Case Study]
        GROUP BY Region
        ORDER BY Total_Sales ASC;

________________________________________
3. Appliance Sales in Ontario
   
        SELECT 
        SUM(Sales) AS Appliance_Sales_Ontario
        FROM [KMS Sql Case Study]
        WHERE Product_Sub_Category = 'Appliances'
        AND Province = 'Ontario';

________________________________________
4. Bottom 10 Customers
   
        SELECT TOP 10 
        Customer_Name, 
        SUM(Sales) AS Total_Sales
        FROM [KMS Sql Case Study]
        GROUP BY Customer_Name
        ORDER BY Total_Sales ASC;
________________________________________
5. Shipping Method with Highest Cost
   
        SELECT 
        Ship_Mode, 
        SUM(Shipping_Cost) AS Total_Shipping_Cost
        FROM [KMS Sql Case Study]
        GROUP BY Ship_Mode
        ORDER BY Total_Shipping_Cost DESC;

Insight: Delivery Truck incurred the highest shipping cost.
________________________________________
6. Most Valuable Customers
   
        SELECT TOP 10 
        Customer_Name, 
        SUM(Sales) AS Total_Sales
        FROM [KMS Sql Case Study]
        GROUP BY Customer_Name
        ORDER BY Total_Sales DESC;
   
Insight: These customers can be nurtured with loyalty programs.









   

   
   



    

