# Sales_Insights_usingPowerBi-SQL
This is a comprehensive Sales Insight Dashboard which I have created using Power Bi and SQL. The goal of this project is to analyze and visualize sales data for a retail company to uncover meaningful insights and support data-driven decision-making.

This project showcases my skills in data extraction,SQL-based transformations, data modelling and Power Bi visualization.

Detailed explaination of the work done by me in this project are as following:

# MySQL:
a) Connected to a MySQL database to query raw sales data.
b) Used the INNER JOIN to connect the 'Transactions' Table and 'Date' Table to query the database in comprehensive manner. 
# SELECT sales.transactions.*,sales.date.* FROM sales.transactions INNER JOIN sales.date ON sales.transactions.order_date=sales.date.date;#
c) Used the 'SUM' function to get an idea of overall revenue made by the Company over the 4 year time period(2017-2020) and        also wrote year-wise specific query to find the revenue made in each of the years (viz. 2017,2018,2019,2020)
# SELECT SUM(sales.transactions.sales_amount) FROM sales.transactions INNER JOIN sales.date ON sales.transactions.order_date = sales.date.date where sales.date.year=2018;#
d)Exported the final query results to Power Bi for visualization.

# PowerBi 
a)Imported data into Power Bi Desktop .
b)Created relationships between dimension and fact table(star schema)
c)In Table View, noticed two transactions done in USD, therefore, created a new column in sales.transactions table using the 'conditional column' feature and named it as norm_sales_amount in which the sales amount was stored in INR only.
# Table.AddColumn(#"Filtered Rows","norm_sales_amount",each if[currency] = "USD" then[sales_amount]*75 else[sales_amount])
The above steps helped me in Data cleaning and in the ETL process.

Process of building my Power Bi Dashboard:
i) Created a new Table named, 'BaseMeasures' and created a new measures which are 'Revenue' and 'Sales Quantity'
# Revenue = SUM('sales transactions'[sales_amount])
# Sales Quantity = SUM('sales transactions' [sales_qty]) 
ii)Visualized the following on dashboard:
'Sales Qunatity by Markets' as 'Clustered Bar Chart'
'Revenue by Markets' as 'Clustered Bar Chart'
'Year' as 'Slicer'
'Revenue Trends' as 'Line Chart'
'Revenue' as 'Card(new)'
'Sales Quantity' as 'Card(new)'
'Top Customers' as 'Pie Chart', showing only top 5 customers
'Top Products' as 'Pie Chart', showing only top 5 products.

Conclusion:
This project delivers the insight the Retail Company seeks in order to analyse the following:
# Its retail-sales over the period of 4 years. 
# The markets which have under-performed, moderately-performed and those who are performing well
# The project also highlights its top customers 
# The project also showcases the top products which have performed well in the market 
# Product-wise, location-specific and customer-specific analysis 

Hence, these key insights have been the main focus deliverables.
