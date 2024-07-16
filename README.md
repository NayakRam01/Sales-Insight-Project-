# Sales-Insight-Project-
this project is about a hardware commpany 
Aims grid principle is used for barin storming, which includes 4 components 
      - Purpose = To unlock sales insights that are not visible before for sales team for decision support & automate them to reduced manual time spent in data gathering.
      - stakeholders =
          * sales director 
          * Marketing team 
          * customer service team 
          * data analytics team 
          * IT team 
      - End Result = an automated dashboard providing quick and latest sales insights in order to support data driven decision making 
      - sucess criteria = 
            * Dashboard(s) uncovering sales order insights with latest data available
            • Sales team able to take better decisions & prove 10% cost savings of total spend
            • Sales Analysts stop data gathering manually in order to save 20% of their business time and reinvest it value added activity


what IT team does is that they maintain the sales management software system (finance,products,critical information)
what data analyst team does is hook tableau with the mysql database to perfrom analysis 
here my sql database and software management system are called OLTP (online tracastional processing system) where day to day sales are recorded 
what DA does is that they use the copy of the dataset that is data warehouse so the actual databases is not disturbed for smooth functioning of the business, this datawarehouse is called OLAP (online analyttical processing system)


we performe ETL(extract transform load)
so we plugged mysql with tableau [or you can export it to csv format] then retrieved the data, created star schema and performed etl 

![image](https://github.com/user-attachments/assets/5a351f62-ac2e-4413-b19d-e27820f6a4cb)



### Data Analysis Using SQL

1. Show all customer records

    `SELECT * FROM customers;`

1. Show total number of customers

    `SELECT count(*) FROM customers;`

1. Show transactions for Chennai market (market code for chennai is Mark001

    `SELECT * FROM transactions where market_code='Mark001';`

1. Show distrinct product codes that were sold in chennai

    `SELECT distinct product_code FROM transactions where market_code='Mark001';`

1. Show transactions where currency is US dollars

    `SELECT * from transactions where currency="USD"`

1. Show transactions in 2020 join by date table

    `SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;`

1. Show total revenue in year 2020,

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";`
	
1. Show total revenue in year 2020, January Month,

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");`

1. Show total revenue in year 2020 in Chennai

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020
and transactions.market_code="Mark001";`
