## Employees from Dept 10 earning more than ANY employee in other departments
```sql
SELECT ENAME
FROM EMPLOYEE
WHERE DEPTNO = 10
AND SAL > ANY (
    SELECT SAL
    FROM EMPLOYEE
    WHERE DEPTNO <> 10
);
```
## Employees from Dept 10 earning more than ALL employees in other departments
```sql
SELECT ENAME
FROM EMPLOYEE
WHERE DEPTNO = 10
AND SAL > ALL (
    SELECT SAL
    FROM EMPLOYEE
    WHERE DEPTNO <> 10
);
```
## Employees in SALES department with Grade 3
```sql
SELECT E.*
FROM EMPLOYEE E
JOIN DEPARTMENT D ON E.DEPTNO = D.DEPTNO
JOIN SALGRADE S ON E.SAL BETWEEN S.LOSAL AND S.HISAL
WHERE D.DNAME = 'SALES'
AND S.GRADE = 3;
```
## Employees who are not managers but manage someone
```sql
SELECT E.ENAME
FROM EMPLOYEE E
WHERE E.JOB <> 'MANAGER'
AND E.EMPNO IN (
    SELECT MGR FROM EMPLOYEE WHERE MGR IS NOT NULL
);
```
## Employees whose manager name is JONES
```sql
SELECT E.ENAME
FROM EMPLOYEE E
JOIN EMPLOYEE M ON E.MGR = M.EMPNO
WHERE M.ENAME = 'JONES';
```
## Employees working in SALES department
```sql
SELECT E.ENAME
FROM EMPLOYEE E
JOIN DEPARTMENT D ON E.DEPTNO = D.DEPTNO
WHERE D.DNAME = 'SALES';
```
## Employee name, dept name, salary & comm (Salary between 2000–5000 & Location Chicago)
```sql
SELECT E.ENAME,
       D.DNAME,
       E.SAL,
       E.COMM
FROM EMPLOYEE E
JOIN DEPARTMENT D ON E.DEPTNO = D.DEPTNO
WHERE E.SAL BETWEEN 2000 AND 5000
AND D.LOC = 'CHICAGO';
```
## Employees whose salary is greater than their manager's salary
```sql
SELECT E.ENAME
FROM EMPLOYEE E
JOIN EMPLOYEE M ON E.MGR = M.EMPNO
WHERE E.SAL > M.SAL;
```
## Employees working in same department as their manager
```sql
SELECT E.ENAME
FROM EMPLOYEE E
JOIN EMPLOYEE M ON E.MGR = M.EMPNO
WHERE E.DEPTNO = M.DEPTNO;
```
## Grade & employee name (Dept 10 or 30, Grade not 4, Joined before 31-Dec-82)
```sql
SELECT E.ENAME,
       S.GRADE
FROM EMPLOYEE E
JOIN SALGRADE S ON E.SAL BETWEEN S.LOSAL AND S.HISAL
WHERE E.DEPTNO IN (10,30)
AND S.GRADE <> 4
AND E.HIREDATE < '1982-12-31';
```
