# DataAnalysis_Project
Python, SQL, Excel, ETL, PowerBI 

**/* Show all customer records */**

select * from customers

**/* Show total number of customers */**

select count(*) from customers

**/* Show transactions for Chennai market (market code for chennai is Mark001 */**

select * from transactions 
where market_code = 'Mark001'

**/* Show distinct product codes that were sold in chennai (77) */ **

select distinct product_code from transactions
where market_code = 'Mark001'

**/*Show transactions where currency is US dollars */**

select * from transactions
where currency = 'USD'

**/*Show transactions in 2020 join by date table */**

select * from date

select * from transactions
join date on transactions.order_date = date.date
where date.year = '2020'

**/* Show total revenue in year 2020, */**

select sum(transactions.sales_amount) as Total_Revenue_2020
from transactions
join date on transactions.order_date = date.date
where date.year ='2020'

**/*Show total revenue in year 2020, January Month, */**

select sum(transactions.sales_amount) as Jan_total_reve_2020
from transactions
join date on transactions.order_date = date.date
where date.month_name = 'January' and date.year = '2020'


**/*Show total revenue in year 2020 in Chennai*/**

select sum(transactions.sales_amount) as Chennai_total_reve_2020
from transactions
join date on transactions.order_date = date.date
where date.year = '2020' and transactions.market_code = 'Mark001'

