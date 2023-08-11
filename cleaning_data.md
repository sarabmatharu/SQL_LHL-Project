What issues will you address by cleaning the data?

What issues will you address by cleaning the data?
Data cleaning is very important while working with data. If data is not clean we can’t get efficient results from our dataset.  
To clean any dataset, first step is to review all data in our database. Data Cleaning helps us to remove any unwanted data from out data base, identify duplicate data, converting data to correct format where needed.
Here are the issues that we can address while doing Data Cleaning: 
1.	Remove any irrelevant data including duplicate data.
2.	Make sure data types are accurate.
3.	Identifying any Missing Values, if too many missing values in one column then we can also delete that column.
4.	Fixing Typos


Queries:
Below, provide the SQL queries you used to clean your data.

Queries : Sales_by_sku

## Checking for Dupes:
    select count(distinct(productsku)) as unique from sales_by_sku

    I used this query to return number of unique rows from table. As I can see query count matches with number of rows, so I know there is no duplicate row in this table.
 
## Next step is to check data types for each column.
   Using psql command \d sales_by_sku
 
   As total order should be integer, so now changing data type for this. 
   Using pgadmin table properties, I made productsku column as primary key. 
   ALTER TABLE sales_by_sku ALTER COLUMN total_ordered TYPE INT  USING total_ordered::integer;

## Missing values : 
    SELECT 
    SUM(CASE WHEN productsku IS NULL THEN 1 ELSE 0 END) AS productskunull, 
    SUM(CASE WHEN total_ordered IS NULL THEN 1 ELSE 0 END) AS Totalorederednull
    FROM sales_by_sku;

    Used column alias name for column headers : 
     I used similar types for queries to clean all tables.





