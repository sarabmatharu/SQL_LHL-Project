What are your risk areas? Identify and describe them.

Data validation is the very important step while dealing with data. In data validation we are checking accuracy & quality of data. In data validation process we are checking to make sure data is complete & we have no blank or null values. We also need to make sure that we have unique vales in our columns, this goes in both ways, to remove duplicate data & also making sure that we have a unique column which we can use to form Primary & Foreign keys. We also need to make sure that data is consistent.

QA Process:
Describe your QA process and include the SQL queries used to execute it.

SELECT *
FROM information_schema.tables
WHERE table_schema = 'public';

