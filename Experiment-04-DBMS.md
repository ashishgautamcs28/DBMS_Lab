## Display the list of employees who have joined the company before 30th June 1980 or after 31st Dec 1981
```sql
SELECT ENAME, HIREDATE
FROM `2cse21_729`
WHERE HIREDATE < '1980-06-30'
OR HIREDATE > '1981-12-31';
```
## Display the names of employees whose names have second alphabet A in their names
```sql
SELECT ENAME
FROM `2cse21_729`
WHERE ENAME LIKE '_A%';
```
## Display the names of employees whose name is exactly five characters in length
```sql
SELECT ENAME
FROM `2cse21_729`
WHERE ENAME LIKE '_____';
```
## Display the names of employees whose names have second alphabet A in their names
```sql
SELECT ENAME
FROM `2cse21_729`
WHERE ENAME LIKE '_A%';
```
## Display the names of employees who are not working as salesman or clerk or analyst
```sql
SELECT ENAME
FROM `2cse21_729`
WHERE JOB NOT IN ('SALESMAN', 'CLERK', 'ANALYST');
```
## Display the name of the employee along with their annual salary (sal*12). The highest salary should appear first
```sql
SELECT ENAME, (SAL * 12) AS ANNUAL_SALARY
FROM `2cse21_729`
ORDER BY ANNUAL_SALARY DESC;
```
## Display name, sal, hra, pf, da, totalsal for each employee
```sql
SELECT 
    ENAME,
    SAL,
    (SAL * 0.15) AS HRA,
    (SAL * 0.10) AS DA,
    (SAL * 0.05) AS PF,
    ((SAL + (SAL * 0.15) + (SAL * 0.10)) - (SAL * 0.05)) AS TOTALSAL
FROM `2cse21_729`
ORDER BY TOTALSAL;
```
## Update the salary of each employee by 10% increment who are not eligible for commission
```sql
UPDATE `2cse21_729`
SET SAL = SAL + (SAL * 0.10)
WHERE COMM IS NULL;
``` 
## Display those employees whose salary is more than 3000 after giving 20% increment
```sql
SELECT ENAME, (SAL * 1.20) AS INCREMENTED_SALARY
FROM `2cse21_729`
WHERE (SAL * 1.20) > 3000;
```
## Display those employees whose salary contains at least 3 digits
```sql
SELECT ENAME, SAL
FROM `2cse21_729`
WHERE SAL BETWEEN 100 AND 9999;
```
