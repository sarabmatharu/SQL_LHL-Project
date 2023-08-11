What are your risk areas? Identify and describe them.

Data validation is the very important step while dealing with data. In data validation we are checking accuracy & quality of data. In data validation process we are checking to make sure data is complete & we have no blank or null values. We also need to make sure that we have unique vales in our columns, this goes in both ways, to remove duplicate data & also making sure that we have a unique column which we can use to form Primary & Foreign keys. We also need to make sure that data is consistent.

QA Process:
Describe your QA process and include the SQL queries used to execute it.

Data Profiling:
My first step was to Identify schema of database. Data profiling provides information on the characteristics of a database, such as rows, columns, average values. It helps to discover data, Understand data characteristics, giving more confidence to trust data
understadning database also helps us to avoid any errors. 
Avohelps us avoid such assumptions. Afer understanding data we can also imrove data where needed.

## identify schema
 SELECT *
 FROM information_schema.tables
 WHERE table_schema = 'public';

## Data Types & Nullability - Check data types of columns & also nullability.

 SELECT column_name, data_type, is_nullable
 FROM information_schema.columns
 WHERE table_name = 'all_sessions';

## Data Validation - Checking for duplicate data

 SELECT fullvisitorid, COUNT(*)
 FROM public.all_sessions
 GROUP BY fullvisitorid
 HAVING COUNT(*) > 1;





