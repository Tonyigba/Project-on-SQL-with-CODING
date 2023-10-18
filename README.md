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
6. RETURNING TOTAL SALES OF CITIES THAT GENERATED TOTAL SALES THAT IS GREATER THAN 20000;
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

