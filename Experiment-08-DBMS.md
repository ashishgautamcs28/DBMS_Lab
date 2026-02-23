## Display all employees with their department name
```sql
SELECT E.ENAME, D.DNAME
FROM EMPLOYEE E
JOIN DEPARTMENT D
ON E.DEPTNO = D.DEPTNO;
```
## Employees whose manager name is 'JONES' (also display manager name)
```sql
SELECT E.ENAME AS Employee,
       M.ENAME AS Manager
FROM EMPLOYEE E
JOIN EMPLOYEE M
ON E.MGR = M.EMPNO
WHERE M.ENAME = 'JONES';
```
## Employee name, job, dept name, manager name, grade (Dept-wise)
```sql
SELECT E.ENAME,
       E.JOB,
       D.DNAME,
       M.ENAME AS Manager,
       S.GRADE
FROM EMPLOYEE E
JOIN DEPARTMENT D ON E.DEPTNO = D.DEPTNO
LEFT JOIN EMPLOYEE M ON E.MGR = M.EMPNO
JOIN SALGRADE S ON E.SAL BETWEEN S.LOSAL AND S.HISAL
ORDER BY D.DEPTNO;
```
## List employees except ‘CLERK’ (Sorted by highest salary)
```sql
SELECT E.ENAME,
       E.JOB,
       S.GRADE,
       D.DNAME,
       E.SAL
FROM EMPLOYEE E
JOIN DEPARTMENT D ON E.DEPTNO = D.DEPTNO
JOIN SALGRADE S ON E.SAL BETWEEN S.LOSAL AND S.HISAL
WHERE E.JOB <> 'CLERK'
ORDER BY E.SAL DESC;
```
## Display employee name, job & manager (include employees without manager)
```sql
SELECT E.ENAME,
       E.JOB,
       COALESCE(M.ENAME, 'No Manager') AS Manager
FROM EMPLOYEE E
LEFT JOIN EMPLOYEE M
ON E.MGR = M.EMPNO;
```
## Employees who earn 36000 per year OR not clerks (Annual salary = SAL * 12)
```sql
SELECT E.ENAME,
       E.JOB,
       (E.SAL*12) AS Annual_Salary,
       E.DEPTNO,
       D.DNAME,
       S.GRADE
FROM EMPLOYEE E
JOIN DEPARTMENT D ON E.DEPTNO = D.DEPTNO
JOIN SALGRADE S ON E.SAL BETWEEN S.LOSAL AND S.HISAL
WHERE (E.SAL*12 = 36000) OR E.JOB <> 'CLERK';
```
## Employees who earn 30000 per year AND not clerks
```sql
SELECT E.ENAME,
       E.JOB,
       (E.SAL*12) AS Annual_Salary,
       E.DEPTNO,
       D.DNAME,
       S.GRADE
FROM EMPLOYEE E
JOIN DEPARTMENT D ON E.DEPTNO = D.DEPTNO
JOIN SALGRADE S ON E.SAL BETWEEN S.LOSAL AND S.HISAL
WHERE (E.SAL*12 = 30000)
AND E.JOB <> 'CLERK';
```
## Employees with their manager name & number (Display 'No Manager')
```sql
SELECT E.EMPNO,
       E.ENAME,
       COALESCE(M.EMPNO, '---') AS Manager_No,
       COALESCE(M.ENAME, 'No Manager') AS Manager_Name
FROM EMPLOYEE E
LEFT JOIN EMPLOYEE M
ON E.MGR = M.EMPNO;
```
## Select dept name, dept no and sum of salary
```sql
SELECT D.DNAME,
       D.DEPTNO,
       SUM(E.SAL) AS Total_Salary
FROM EMPLOYEE E
JOIN DEPARTMENT D
ON E.DEPTNO = D.DEPTNO
GROUP BY D.DEPTNO, D.DNAME;
```
## Display employee number, name and department location
```sql
SELECT E.EMPNO,
       E.ENAME,
       D.LOC
FROM EMPLOYEE E
JOIN DEPARTMENT D
ON E.DEPTNO = D.DEPTNO;
```
## Display employee name and department name
```sql
SELECT E.ENAME,
       D.DNAME
FROM EMPLOYEE E
JOIN DEPARTMENT D
ON E.DEPTNO = D.DEPTNO;
```