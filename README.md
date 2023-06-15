# Portfolio-Projects
Analysis of retail store data using SQL, Excel and Tableau
In this project, I extracted data from SQL, analyzed it in Excel and visualized it in Tableau
For extraction of data in SQL and combining various tables for analysis, the code below was used:
SQL Script for Data Tables
SELECT 
 ord.order_id,
 CONCAT(cus.First_name, ' ',cus.last_name) AS 'Customers',
 cus.city,
 cus.state,
 ord.order_date,
 SUM(ite.Quantity) AS 'Total_Units',
 SUM(ite.Quantity*ite.list_price) AS 'revenue',
 pro.product_name,
 cat.Category_name,
 sto.store_name,
 CONCAT(sta.First_name,' ',sta.last_name) AS 'Sales_rep'
FROM Sales.orders ord
Join sales.customers cus
ON ord.customer_id=cus.customer_id
Join sales.order_items ite
ON ord.order_id=ite.order_id
Join production.products pro
ON ite.product_id=pro.product_id
JOIN Production.categories cat
ON pro.category_id=cat.category_id
Join sales.stores sto
ON ord.store_id=sto.store_id
JOIN sales.staffs sta
ON Ord.staff_id=sta.staff_id
GROUP BY 
 ord.order_id,
 CONCAT(cus.First_name, ' ',cus.last_name),
 cus.city,
 cus.state,
 ord.order_date,
 pro.product_name,
 cat.Category_name,
 sto.store_name,
 CONCAT(sta.First_name,' ',sta.last_name)
After joining multiple tables with critical insights for the analysis, a brief like the image below is obtained.
SQL Data Extract
 
The SQL dataset was consequently connected to an Excel workbook, where pivot tables were created as a basis for a comprehensive dashboard. A dashboard showing total annual revenue, monthly revenue, revenue per product category, each store’s revenue, revenue per sales person and top ten customers was designed.
Excel Dashboard
 
Tableau Dashboard
 
Insights
• Total revenue for the three years was $8,578,989, from the sale of 7,078 bicycles to 1,444 customers.
• 2017 had the highest revenue at $3,845,515 from selling 3,099 units to 684 customers.
• April had the highest sales at $1,350,509 revenue, while July had the lowest revenue at $491,532.
• Baldwin Bikes constituted 68% of total revenue, with Santa Cruz Bikes at 21% and the least proportion of revenue was from Rowlett bikes with 11%.
• The product category with the highest revenue was mountain bikes at 35.33%, followed by road bikes at 21.59% and cruisers bikes with 12.93%.

