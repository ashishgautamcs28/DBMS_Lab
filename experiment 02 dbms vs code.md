## CREATE TABLE 2cse21_729
```sql
CREATE TABLE `2cse21_729` AS
SELECT * FROM EMPLOYEE;
SELECT * FROM `2cse21_729`;
```
##  List all distinct job in Employee
```sql
SELECT DISTINCT JOB
FROM `2cse21_729`;
```

## List all information about employee in Department Number 30
```sql
SELECT *
FROM `2cse21_729`
WHERE DEPTNO = 30;
```

## Find all department number greater than 20
```sql
SELECT DEPTNO
FROM `2cse21_729`
WHERE DEPTNO > 20;
```

## Find all information about all the managers as well as the clerks in department 30
```sql
SELECT *
FROM `2cse21_729`
WHERE DEPTNO = 30
AND (JOB = 'MANAGER' OR JOB = 'CLERK');
```

## List the Employee name, Employee numbers and department of all clerks
```sql
SELECT ENAME, EMPNO, DEPTNO
FROM `2cse21_729`
WHERE JOB = 'CLERK';
```

## Find all managers not in department 30
```sql
SELECT *
FROM `2cse21_729`
WHERE JOB = 'MANAGER'
AND DEPTNO <> 30;
```

## List information about all Employees in department 10 who are not manager or clerks
```sql
SELECT *
FROM `2cse21_729`
WHERE DEPTNO = 10
AND JOB NOT IN ('MANAGER', 'CLERK');
```

## Find Employees and jobs earning between 1200 and 1400
```sql
SELECT ENAME, JOB
FROM `2cse21_729`
WHERE SAL BETWEEN 1200 AND 1400;
```

## List Name and Department Number of employee who are clerks, analyst or salesman
```sql
SELECT ENAME, DEPTNO
FROM `2cse21_729`
WHERE JOB IN ('CLERK', 'ANALYST', 'SALESMAN');
```

## List Name and Department Number of employee whose names began with M
```sql
SELECT ENAME, DEPTNO
FROM `2cse21_729`
WHERE ENAME LIKE 'M%';
```