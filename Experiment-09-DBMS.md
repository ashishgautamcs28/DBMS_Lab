## Display the name of employee who earns highest salary
```sql
SELECT ENAME
FROM EMPLOYEE
WHERE SAL = (SELECT MAX(SAL) FROM EMPLOYEE);
```
## Employee number & name of clerk earning highest salary among clerks
```sql
SELECT EMPNO, ENAME
FROM EMPLOYEE
WHERE JOB = 'CLERK'
AND SAL = (
    SELECT MAX(SAL)
    FROM EMPLOYEE
    WHERE JOB = 'CLERK'
);
```
## Salesman earning more than highest salary of any clerk
```sql
SELECT ENAME
FROM EMPLOYEE
WHERE JOB = 'SALESMAN'
AND SAL > (
    SELECT MAX(SAL)
    FROM EMPLOYEE
    WHERE JOB = 'CLERK'
);
```


## Clerks who earn more than JAMES and less than SCOTT
```sql
SELECT ENAME
FROM EMPLOYEE
WHERE JOB = 'CLERK'
AND SAL > (SELECT SAL FROM EMPLOYEE WHERE ENAME = 'JAMES')
AND SAL < (SELECT SAL FROM EMPLOYEE WHERE ENAME = 'SCOTT');
```
## Employees who earn more than JAMES OR more than SCOTT
```sql
SELECT ENAME
FROM EMPLOYEE
WHERE SAL > (SELECT SAL FROM EMPLOYEE WHERE ENAME = 'JAMES')
OR SAL > (SELECT SAL FROM EMPLOYEE WHERE ENAME = 'SCOTT');
```
## Employees earning highest salary in their respective departments
```sql
SELECT ENAME, DEPTNO, SAL
FROM EMPLOYEE E
WHERE SAL = (
    SELECT MAX(SAL)
    FROM EMPLOYEE
    WHERE DEPTNO = E.DEPTNO
);
```
## Employees earning highest salary in their respective job groups
```sql
SELECT ENAME, JOB, SAL
FROM EMPLOYEE E
WHERE SAL = (
    SELECT MAX(SAL)
    FROM EMPLOYEE
    WHERE JOB = E.JOB
);
```
## Employees working in Accounting department
```sql
SELECT ENAME
FROM EMPLOYEE
WHERE DEPTNO = (
    SELECT DEPTNO
    FROM DEPARTMENT
    WHERE DNAME = 'ACCOUNTING'
);
```
## Employees working in Chicago
```sql
SELECT ENAME
FROM EMPLOYEE
WHERE DEPTNO = (
    SELECT DEPTNO
    FROM DEPARTMENT
    WHERE LOC = 'CHICAGO'
);
```
## Job groups having total salary greater than max salary of managers
```sql
SELECT JOB, SUM(SAL) AS Total_Salary
FROM EMPLOYEE
GROUP BY JOB
HAVING SUM(SAL) > (
    SELECT MAX(SAL)
    FROM EMPLOYEE
    WHERE JOB = 'MANAGER'
);
```

