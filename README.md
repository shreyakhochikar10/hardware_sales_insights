SQL Queries

1. Show all customer records

    SELECT * 
    FROM customers;

1. Show total number of customers

    SELECT count(*) 
    FROM customers;

1. Show transactions for Chennai market (market code for chennai is Mark001)

    SELECT * 
    FROM transactions 
    WHERE market_code='Mark001';

1. Show distrinct product codes that were sold in chennai

    SELECT distinct product_code 
    FROM transactions 
    WHERE market_code='Mark001';

1. Show transactions where currency is US dollars

    SELECT * 
    FROM transactions 
    WHERE currency="USD"

1. Show transactions in 2020 join by date table

    SELECT t.*, date.* 
    FROM transactions AS t
    INNER JOIN date AS d
    ON t.order_date=d.date 
    WHERE date.year=2020;

1. Show total revenue in year 2020,

    SELECT SUM(t.sales_amount) 
    FROM transactions AS t
    INNER JOIN date AS d
    ON t.order_date=d.date 
    WHERE d.year=2020 
    AND t.currency="INR\r" OR t.currency="USD\r";
	
1. Show total revenue in year 2020, January Month,

    SELECT SUM(t.sales_amount) 
    FROM transactions AS t
    INNER JOIN date AS d
    ON t.order_date=d.date 
    WHERE d.year=2020 
    AND d.month_name="January" AND (t.currency="INR\r" OR t.currency="USD\r");

1. Show total revenue in year 2020 in Chennai

    SELECT SUM(t.sales_amount) 
    FROM transactions AS t 
    INNER JOIN date AS d
    ON t.order_date=d.date 
    WHERE d.year=2020
    AND t.market_code="Mark001";
