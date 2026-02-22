## Display the total number of employee working in the company.
```sql
SELECT COUNT(*) AS TOTAL_EMPLOYEES
FROM `2cse21_729`;
```
## Display the total salary being paid to all employees.
```sql
SELECT SUM(SAL) AS TOTAL_SALARY
FROM `2cse21_729`;
```
## Display the maximum salary from employee table.
```sql
SELECT MAX(SAL) AS MAX_SALARY
FROM `2cse21_729`;
```
## Display the minimum salary from employee table.
```sql
SELECT MIN(SAL) AS MIN_SALARY
FROM `2cse21_729`;
```
## Display the average salary from employee table
```sql
SELECT AVG(SAL) AS AVERAGE_SALARY
FROM `2cse21_729`;
```
## Display the maximum salary being paid to clerk.
```sql
SELECT MAX(SAL) AS MAX_CLERK_SALARY
FROM `2cse21_729`
WHERE JOB = 'CLERK';
```
## Display the maximum salary being paid in dept no 20.
```sql
SELECT MAX(SAL) AS MAX_SALARY_DEPT20
FROM `2cse21_729`
WHERE DEPTNO = 20;
```
## Display the minimum salary paid to any salesman.
```sql
SELECT MIN(SAL) AS MIN_SALESMAN_SALARY
FROM `2cse21_729`
WHERE JOB = 'SALESMAN';
```
## Display the average salary drawn by managers.
```sql
SELECT AVG(SAL) AS AVG_MANAGER_SALARY
FROM `2cse21_729`
WHERE JOB = 'MANAGER';
```
## Display the total salary drawn by analyst working in dept no 40.
```sql
SELECT SUM(SAL) AS TOTAL_ANALYST_SALARY
FROM `2cse21_729`
WHERE JOB = 'ANALYST' AND DEPTNO = 40;
```
## Display the names of the employee in Uppercase.
```sql
SELECT UPPER(ENAME) AS EMPLOYEE_NAME_UPPER
FROM `2cse21_729`;
```
## Display the names of the employee in Lowercase.
```sql
SELECT LOWER(ENAME) AS EMPLOYEE_NAME_LOWER
FROM `2cse21_729`;
```
## Display the names of the employee in Proper case.
```sql
SELECT CONCAT(UPPER(LEFT(ENAME,1)), LOWER(SUBSTRING(ENAME,2))) AS EMPLOYEE_NAME_PROPER
FROM `2cse21_729`;
``` 
## Display the length of Your name using appropriate function.
```sql
SELECT LENGTH('ASHISH') AS NAME_LENGTH;
```
## Display the length of all the employee names
```sql
SELECT ENAME, LENGTH(ENAME) AS NAME_LENGTH
FROM `2cse21_729`;
```