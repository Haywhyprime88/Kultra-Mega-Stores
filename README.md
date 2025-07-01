# Kultra-Mega-Stores
A complete SQL case study on Kultra Mega Stores (KMS), analyzing sales performance, customer behavior, and operational insights from 2009 to 2012. Includes 11 business questions answered with SQL queries and data-driven recommendations for management.

Kultra Mega Stores - SQL Case Study (2009–2012)

Overview

This case study explores transactional and customer data from Kultra Mega Stores (KMS) using SQL. The goal is to extract business insights from raw data to assist management in making data-informed decisions.

 ## Scenario I
________________________________________
1. Product Category with Highest Sales

    
       SELECT TOP 1
        Product_Category, 
        SUM(Sales) AS Total_Sales
        FROM [KMS Sql Case Study]
        GROUP BY Product_Category
        ORDER BY Total_Sales DESC;
   
   Technology has the highest sale with	5,984,248 sold

________________________________________
2. Top 3 and Bottom 3 Regions by Sales
   
-- Top 3 Regions

        SELECT TOP 3 Region,
        SUM(Sales) AS Total_Sales
        FROM [KMS Sql Case Study]
        GROUP BY Region
        ORDER BY Total_Sales DESC;

West:	3,597,549.41
Ontario:	3,063,212.60
Prarie:	2,837,304.60

-- Bottom 3 Regions

        SELECT TOP 3 Region,
        SUM(Sales) AS Total_Sales
        FROM [KMS Sql Case Study]
        GROUP BY Region
        ORDER BY Total_Sales ASC;

Nunavut: 116,376.47
Northwest: Territories	800,847.35
Yukon:	975,867.39
________________________________________
3. Appliance Sales in Ontario
   
        SELECT 
        SUM(Sales) AS Appliance_Sales_Ontario
        FROM [KMS Sql Case Study]
        WHERE Product_Sub_Category = 'Appliances'
        AND Province = 'Ontario';
   
Appliance Sales Ontario: 202,346.84
___________________________________________
4. Advise the management of KMS on what to do to increase the revenue from the bottom customers 
   ________________________________________
5. KMS incurred the most shipping cost using which shipping method?

       SELECT TOP 1 Ship_Mode, 
       SUM(Shipping_Cost) AS Total_Shipping_Cost
       FROM [KMS Case Study]
       GROUP BY Ship_Mode
       ORDER BY Total_Shipping_Cost DESC;

   Delivery Truck:	51,971.94
   
## Scenario II
________________________________________
6. Who are the most valuable customers, 
and what products or services do they typically 
purchase

       SELECT TOP 10 Customer_Name, 
       Product_Category,
       COUNT(Order_ID) AS Order_Count,
       SUM(Sales) AS Total_Sales
       FROM [KMS Case Study]
       GROUP BY Customer_Name, Product_Category
       ORDER BY Total_Sales DESC;

Emily Phan	       Technology	     4	 110481.96
Deborah Brumfield	Technology	     8	 76795.80
Dennis Kane	      Technology	     9	 60434.64
Jasper Cacioppo  	Technology	     3	 57739.27
Clytie Kelty	     Technology	     7	 54454.95
Raymond Book	     Technology	     4	 53450.78
Lisa DeCherney	   Furniture	      8	 52477.37
Alejandro Grove  	Office Supplies	8	 51696.02
Grant Carroll	    Office Supplies	15	50837.27
Roy Skaria	       Furniture	      8	 50177.24
________________________________________
7. Top Small Business Customer
   
        SELECT TOP 1 Customer_Name, 
        SUM(Sales) AS Total_Sales
        FROM [KMS Sql Case Study]
        WHERE Customer_Segment = 'Small Business'
        GROUP BY Customer_Name
        ORDER BY Total_Sales DESC;
   
   Dennis Kane,	is the small business customer with the highest sale: 75,967.59

Insight: These customers can be nurtured with loyalty programs.
________________________________________
8. Which Corporate customer made the most orders from 2009 to 2012?
   
        SELECT TOP 1 Customer_Name, 
        COUNT(*) AS Total_Orders
        FROM [KMS Case Study]
        WHERE Customer_Segment = 'Corporate'
        GROUP BY Customer_Name
        ORDER BY Total_Orders DESC;
   
   Adam Hart placed the most number of orders 27
________________________________________
9. Who is the most profitable consumer customer?

        SELECT TOP 1 Customer_Name, 
        SUM(Profit) AS Total_Profit
        FROM [KMS Case Study]
        WHERE Customer_Segment = 'Consumer'
        GROUP BY Customer_Name
        ORDER BY Total_Profit DESC;

Emily Phan is the most profitable customer	34,005.44
________________________________________
10. Who returned items, and what customer segment do they belong to?

    	SELECT DISTINCT 
        k.Customer_Name, 
        k.Customer_Segment
        FROM [KMS Case Study] k
        JOIN KMS_RETURN r 
        ON k.Order_ID = r.[Order_ID];

________________________________________
11. If the delivery truck is the most economical but the slowest shipping method and 
Express Air is the fastest but the most expensive one, do you think the company appropriately spent shipping costs based on the Order Priority? Explain your answer 
       

## 🛠 Tools Used

•	Microsoft SQL Server

•	Excel (for return data verification)

## Key Takeaways

•	SQL enables fast and scalable sales insights

•	Segment-based strategies are essential for marketing and retention

•	Shipping operations need better alignment with priority levels
________________________________________

Prepared by: **Arinde Ayooluwa**

Date: July 27,2025.
   









   










   

   
   



    

