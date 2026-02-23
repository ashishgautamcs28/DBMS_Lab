## List all employees and jobs in Department 30 in descending order by salary
```sql
SELECT ENAME, JOB
FROM `2cse21_729`
WHERE DEPTNO = 30
ORDER BY SAL DESC;
```
## List job and Department Number of employees whose name are five letters long begin with “A” and end with “N”
```sql
SELECT JOB, DEPTNO
FROM `2cse21_729`
WHERE ENAME LIKE 'A___N';
```
## Display the name of employees whose name start with alphabet S
```sql
SELECT ENAME
FROM `2cse21_729`
WHERE ENAME LIKE 'S%';
```
## Display the names of employees whose name ends with alphabet S
```sql
SELECT ENAME
FROM `2cse21_729`
WHERE ENAME LIKE '%S';
```
## Display the names of employees working in department number 10 or 20 or 40 or employees working as clerks, salesman or analyst
```sql
SELECT ENAME
FROM `2cse21_729`
WHERE DEPTNO IN (10, 20, 40)
OR JOB IN ('CLERK', 'SALESMAN', 'ANALYST');
```
## Display employee number and names for employees who earn commission
```sql
SELECT EMPNO, ENAME
FROM `2cse21_729`
WHERE COMM IS NOT NULL;
```
## Display employee number and total salary for each employee
```sql
SELECT EMPNO, (SAL + IFNULL(COMM,0)) AS TOTAL_SALARY
FROM `2cse21_729`;
```
## Display employee number and annual salary for each employee
```sql
SELECT EMPNO, (SAL * 12) AS ANNUAL_SALARY
FROM `2cse21_729`;
```
## Display the names of all employees working as clerks and drawing a salary more than 3,000
```sql
SELECT ENAME
FROM `2cse21_729`
WHERE JOB = 'CLERK'
AND SAL > 3000;
```
## Display the names of employees who are working as clerk, salesman or analyst and drawing a salary more than 3,000
```sql
SELECT ENAME
FROM `2cse21_729`
WHERE JOB IN ('CLERK', 'SALESMAN', 'ANALYST')
AND SAL > 3000;
```
