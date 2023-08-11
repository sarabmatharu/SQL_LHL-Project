## Question 1: Search units sold by visit number.

SQL Queries: 
select visitid, units_sold from analytics where units_sold > 5 order by visitid

Answer : This query is serahing for units sold & ordering by visitid.

## Question 2: select names of product where stock level is greater than 1000

SQL Queries: select stocklevel, name from public.sales_report where stocklevel > 1000

Answer : Products with stock level greater than 1000

## Question 3: Find total number of unique visitors

SQL Queries: 
select count(distinct fullvisitorid) from all_sessions

Answer : All Unique visitors

## Question 4: find all duplicate records

SQL Queries: 
SELECT userid, units_sold, 
 COUNT(*) AS Count
FROM analytics
GROUP BY userid, units_sold
HAVING COUNT(*) > 1;

Answer : Duplicate Records

## Question 5: Select sales for india

SQL Queries:
select channelgrouping, count(channelgrouping) as groupcount from all_sessions 
where country = 'India' group by channelgrouping

Sales for India