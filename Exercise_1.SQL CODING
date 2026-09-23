--create a catalog 
CREATE CATALOG IF NOT EXISTS karabohope;
--create a schema 
CREATE SCHEMA IF NOT EXISTS karabohope.default;
-- create table with deduplicated data (this will remove duplicates)
CREATE OR REPLACE TABLE karabohope.default.bronze(
  id INT,
  First_name STRING,
  Last_name STRING,
  Department STRING,
  Salary STRING,
  Hire_data STRING,
  City STRING
);
-- insert data (run this only once)
INSERT INTO karabohope.default.bronze VALUES 
  (1,'ALICE','GREEN','IT','7000','2020-01-10','Johannesburg'), 
  (2,'BRIAN','LEE','HR','45000','2019-03-22','Cape Town'), 
  (3,'CATHY','ZULU','Finance','65000','2018-07-18','Durban'), 
  (4,'DAVID','MOKOENA','Marketing','50000','2021-11-05','Pretoria'), 
  (5,'EVA','NAIDOO','IT','72000','2017-09-30','Johannesburg');

-- Question 1: retrieve all columns from the employees table
SELECT DISTINCT *
FROM karabohope.default.bronze;

--Question 2: find all unique departments  
SELECT DISTINCT Department
FROM karabohope.default.bronze;

--Question 3: retrieve first and last names ordered by salary descending 
SELECT First_name, Last_name, Salary
FROM karabohope.default.bronze
ORDER BY Salary DESC;

--Question 4: retrieve the top 3 highest paid employees 
SELECT ID, First_name , Last_name , Salary 
FROM karabohope.default.bronze
ORDER BY Salary DESC
 LIMIT 3;

 --Question 5: find employees in the IT department 
 SELECT ID, First_name , Last_name , Department 
 FROM karabohope.default.bronze
 WHERE Department='IT'

 --Question 6: find employees in finance with salary >60000
 SELECT ID,First_name , Last_name , Department , Salary 
 FROM karabohope.default.bronze
 WHERE Department='Finance'AND SALARY >60000

 --Question 7: find employees in HR or Marketing 
 SELECT ID,First_name ,Last_name, Department 
 FROM karabohope.default.bronze
 WHERE Department='HR' OR Department= 'Marketing';

 --Question 8: find employees NOT in IT 
 SELECT ID ,First_name ,Last_name,Department
 FROM karabohope.default.bronze
 WHERE Department != 'IT';

--Question 9:find employees in IT,HR OR Finance using IN 
SELECT ID ,First_name ,Last_name ,Department
FROM karabohope.default.bronze
WHERE Department IN ('IT','HR','Finance');

--Question 10: find employees in IT with salary>65000 and city Johannesburg
SELECT ID ,First_name ,Last_name ,Department ,Salary ,City
FROM karabohope.default.bronze
WHERE Department= 'IT' AND Salary >65000 AND City='Johannesburg';
