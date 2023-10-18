# PROJECT-on-SQL-with-CODING

# INTRODUCTION 
The Employee, Salary, Department, and Superstore1 dataset is valuable for addressing 10 key business questions. This analysis focuses on the writing of CODINGS, CLEANING, ANALYSING, AND HAVING RESULTS of data, intending to have valuable insights into the DATABASE. This analysis will give an understanding of the dataset's performance and opportunities for optimization and getting more information on the company's employees.

Problem Statement:
Using the dataset, the TEN key questions generated were;
1. How many employees does the company have?
2. CODE RETURNING TWENTY-FIVE(25) TOP CUSTOMER THAT GENERATED THE MOST SALES ALSO VIEW IT AS A TABLE.
3. Connect two tables to display EMPLOYEE NAME, DOB, EDUCATION, AND DESIGNATION.
4. CONCATENATING two COLUMNS AND RETURNING THEM AS ONE COLUMN.
5. RETURNING FIVE(5) TOP CUSTOMER THAT GENERATED THE MOST PROFIT;
6. CODE CHANGING COLUMN NAME FROM depID TO DeptID;
7. CODE JOINING TWO TABLES TO GET INFO(Base, Name and Dob) WITH THE COMMON COLUMN ID
8. RETURNING EMPLOYEE WHOSE INCREMENT IS GREATER THEN 5000
9. CODE TO SUBQUERY THE CTE AND JOIN TWO TABLE
10. CODE RETURNING NAMES OF ALL THE EMPLOYEES WHOSE CITY IS MUMBAI

USE Sales;
SELECT * FROM employee;
SELECT COUNT(NAME) AS Emp_number
FROM employee;
![SQL PROJT 8 CODE RETURNING NUMBER OF EMPLOYEE IN THE COMPANY](https://github.com/Tonyigba/Project-on-SQL-with-CODING/assets/143624967/766a1a97-ee73-4a44-afd4-9466bc6b4cc6)

USE Sales;
SELECT * FROM superstore1;

-- CODE RETURNIG TWENTY-FIVE(25) TOP CUSTOMER THAT GENERATED THE MOST SALES
SELECT `Customer Name`, ROUND(SUM(Sales), 2) AS Total_Sales
FROM superstore1
GROUP BY `Customer Name`
ORDER BY SUM(Sales) DESC
LIMIT 15;
![SQL PROJT 1-- CODE RETURNIG TWENTY-FIVE(25) TOP PRODUCT THAT GENERATED THE MOST SALES AND STORING THE RESULT AS A TABLE USING CTE](https://github.com/Tonyigba/Project-on-SQL-with-CODING/assets/143624967/e181655e-d53a-4a87-be6a-d7d9481ee642)

USE Sales;
 
SELECT * FROM employee;
SELECT * FROM department;
SELECT Name, dob, city, education, Designation
FROM employee
JOIN department
ON employee.DeptID = department.DeptID;
![SQL PROJT 4 CODE JOINING TWO TABLE TO SHOW THE EMPLOYEE NAME DOB AND CITY JOINING  THE DEPARTMENT TABLE](https://github.com/Tonyigba/Project-on-SQL-with-CODING/assets/143624967/50f71de2-bec4-4e79-a74c-1214032129f3)


USE Sales;

SELECT * FROM employee;

-- CODE CONCATENATING NAME AND FNAME COLUMNS RETURNING THEM AS ONE COLUMN EMLOYEE FULL NAME
SELECT empID, CONCAT(name, " ", fname) AS `Employee Full Name`
FROM employee;


USE Sales;
SELECT * FROM superstore1;

-- CODE RETURNIG FIVE(5) TOP CUSTOMER THAT GENERATED THE MOST PROFIT
 
SELECT `Customer Name`, ROUND(SUM(Profit), 2) AS Total_Profit
FROM superstore1
GROUP BY `Customer Name`
ORDER BY SUM(Profit) DESC
LIMIT 5;
![CODE RETURNIG FIVE(5) TOP CUSTOMER THAT GENERATED THE MOST PROFIT](https://github.com/Tonyigba/Project-on-SQL-with-CODING/assets/143624967/38b11ef1-48e9-4810-bf99-d80c7191e054)

USE Sales;

-- CODE CHANGING COLUMN NAME FROM depID TO DeptID

SELECT * FROM department;
ALTER TABLE department CHANGE depID DeptID INT;
![SQL PROJT 3 -- CODE CHANGING COLUMN NAME FROM depID TO DeptID](https://github.com/Tonyigba/Project-on-SQL-with-CODING/assets/143624967/e508b2ed-ce70-44a5-a085-625de1f7adfe)


USE Sales;
-- CODE JOINING TWO TABLE TO SHOW THE EMPLOYEE NAME, DOB WITH COMMON COLUMN ID
SELECT * FROM employee;
SELECT * FROM department;
SELECT Name, dob, city, education, Designation
FROM employee
JOIN department
ON employee.DeptID = department.DeptID;
![SQL PROJT 3 -- CODE CHANGING COLUMN NAME FROM depID TO DeptID](https://github.com/Tonyigba/Project-on-SQL-with-CODING/assets/143624967/1897312d-ba30-4a59-8ac8-36e0945e585f)

USE Sales;
-- CODE JOINING TWO TABLE TO SHOW THE EMPLOYEE NAME, YEARLY INCREMENT, DOB AND BASE 
-- RETURNING EMPLOYEE WHOSE INCREMENT IS GREATER THEN 5000
SELECT * FROM salary;
SELECT * FROM employee;
SELECT `yearly increment`, Base, name, dob
FROM salary
JOIN employee
ON salary.empID = employee.empID
HAVING `yearly increment` > '5000';
![SQL PROJT 7 CODE JOINING TWO TABLES RETURNING EMPLOYEE WHOSE INCREMENT IS GREATER THEN 5000](https://github.com/Tonyigba/Project-on-SQL-with-CODING/assets/143624967/2ee3f6af-e9fb-4d2b-9f6c-95baa81bb13c)


USE Sales;
SELECT * FROM employee;
-- CODE RETURNING NAMES OF ALL THE EPLOYEE WHOSE CITY IS MUMBAI

WITH `Mumbai Emp` AS
(SELECT empID, NAME, fname, DeptID, city AS Mumbai_city
FROM employee
WHERE city = 'Mumbai')
![SQL PROJT 5 CODE RETURNING NAMES OF ALL THE EPLOYEE WHOSE CITY IS MUMBAI](https://github.com/Tonyigba/Project-on-SQL-with-CODING/assets/143624967/76e8a1fa-89d7-4ac8-965d-2eb37bd8f622)


WITH `Mumbai Emp` AS
(SELECT empID, NAME, fname, DeptID, city AS Mumbai_city
FROM employee
WHERE city = 'Mumbai')

-- CODE TO SUBQUERY THE CTE AND JOINING TWO TABLE RETURNING EmpID, NAME, fName, EDUCATION AND DESIGNATION OF ALL THE EPLOYEE WHOSE CITY IS MUMBAI
SELECT * FROM `Mumbai Emp`;
SELECT * FROM department;
SELECT empID, name, fname, education, Designation
FROM employee
JOIN department
ON employee.DeptID = department.DeptID;![SQL PROJT 6 CODE TO SUBQUERY THE CTE AND JOINING TWO TABLE RETURNING EmpID  NAME fName EDUCATION AND DESIGNATION OF ALL THE EPLOYEE WHOSE CITY IS MUMBAI](https://github.com/Tonyigba/Project-on-SQL-with-CODING/assets/143624967/c2da99d2-6275-4a0a-b059-93b663411fac)

