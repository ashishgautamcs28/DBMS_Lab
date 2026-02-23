## Compute the number of days remaining in this year
```sql
SELECT 
    DATEDIFF(
        STR_TO_DATE(CONCAT(YEAR(CURDATE()),'-12-31'),'%Y-%m-%d'),
        CURDATE()
    ) AS Days_Remaining;
```
## Find the highest and lowest salaries and the difference
```sql
SELECT 
    MAX(SAL) AS Highest_Salary,
    MIN(SAL) AS Lowest_Salary,
    MAX(SAL) - MIN(SAL) AS Salary_Difference
FROM EMPLOYEE;
```
## Employees whose commission > 25% of salary
```sql
SELECT ENAME, SAL, COMM
FROM EMPLOYEE
WHERE COMM > (SAL * 0.25);
```
## Display salary in dollar format
```sql
SELECT ENAME,
       CONCAT('$', FORMAT(SAL,2)) AS Salary_in_Dollar
FROM EMPLOYEE;
```
## Matrix Query (Job-wise salary based on department)
```sql
SELECT JOB,
       SUM(CASE WHEN DEPTNO = 10 THEN SAL ELSE 0 END) AS Dept10,
       SUM(CASE WHEN DEPTNO = 20 THEN SAL ELSE 0 END) AS Dept20,
       SUM(CASE WHEN DEPTNO = 30 THEN SAL ELSE 0 END) AS Dept30,
       SUM(SAL) AS Total_Salary
FROM EMPLOYEE
GROUP BY JOB;
```
## Total Employees + Year-wise Hired Count
```sql
SELECT 
    COUNT(*) AS Total_Employees,
    SUM(YEAR(HIREDATE)=1980) AS Hired_1980,
    SUM(YEAR(HIREDATE)=1981) AS Hired_1981,
    SUM(YEAR(HIREDATE)=1982) AS Hired_1982,
    SUM(YEAR(HIREDATE)=1983) AS Hired_1983
FROM EMPLOYEE;
```
## Get Last Sunday of Any Month
```sql
SELECT 
    DATE_SUB(
        LAST_DAY(CURDATE()),
        INTERVAL (DAYOFWEEK(LAST_DAY(CURDATE())) - 1) DAY
    ) AS Last_Sunday;
```
## Department number & total employees in each department
```sql
SELECT DEPTNO, COUNT(*) AS Total_Employees
FROM EMPLOYEE
GROUP BY DEPTNO;
```
## Various jobs & total employees in each job group
```sql
SELECT JOB, COUNT(*) AS Total_Employees
FROM EMPLOYEE
GROUP BY JOB;
```
## Department numbers & total salary for each department
```sql
SELECT DEPTNO, SUM(SAL) AS Total_Salary
FROM EMPLOYEE
GROUP BY DEPTNO;
```