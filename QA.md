What are your risk areas? Identify and describe them.

Data validation is the very important step while dealing with data. In data validation we are checking accuracy & quality of data. In data validation process we are checking to make sure data is complete & we have no blank or null values. We also need to make sure that we have unique vales in our columns, this goes in both ways, to remove duplicate data & also making sure that we have a unique column which we can use to form Primary & Foreign keys. We also need to make sure that data is consistent.

QA Process:
Describe your QA process and include the SQL queries used to execute it.

SELECT *
FROM information_schema.tables
WHERE table_schema = 'public';

Data Types & Nullability

SELECT column_name, data_type, is_nullable
FROM information_schema.columns
WHERE table_name = 'all_sessions';

Data Validation

Checking for duplicate data

SELECT fullvisitorid, COUNT(*)
FROM public.all_sessions
GROUP BY fullvisitorid
HAVING COUNT(*) > 1;





