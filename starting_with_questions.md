Answer the following questions and provide the SQL queries used to find the answer.
   
**Question 1: Which cities and countries have the highest level of transaction revenues on the site?**

SQL Queries:

select city, country, productrevenue from all_sessions order by city;
SELECT city from all_sessions WHERE productrevenue = (SELECT MAX (productrevenue) FROM all_sessions);
SELECT country from all_sessions WHERE productrevenue = (SELECT MAX (productrevenue) FROM all_sessions);

**Question 2: What is the average number of products ordered from visitors in each city and country?**

SQL Queries:

select distinct city from all_sessions order by city;
select distinct city, country from all_sessions order by country;
select distinct city, country, AVG (productquantity)::NUMERIC(10,2) as avg_products from all_sessions
group by city order by country;

**Question 3: Is there any pattern in the types (product categories) of products ordered from visitors in each city and country?**

SQL Queries:

select city,country, v2productcategory from all_sessions where v2productcategory ='%Home%'
select *  from all_sessions where v2productcategory ='%Home%'

**Question 4: What is the top-selling product from each city/country? Can we find any pattern worthy of noting in the products sold?**

SQL Queries:

select city from all_sessions where (select max (orderedquantity)from products)
where all_sessons.productsku = products.sku

select city from all_sessions where (select max (orderedquantity)from products)
where all_sessons.productsku = products.sku

**Question 5: Can we summarize the impact of revenue generated from each city/country?**

SQL Queries:

select avg(productrevenue) from public.all_sessions


