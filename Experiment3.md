# Experiment 3 – Employee Table Queries

## Query 1: List all employees and their jobs in Department 30 in descending order of salary
```sql
SELECT ename, job, sal
FROM employee
WHERE deptno = 30
ORDER BY sal DESC;
```
---
## Query 2: List job and department number of employees whose names are five letters long, begin with 'A' and end with 'N'
```sql
SELECT job, deptno
FROM employee
WHERE ename LIKE 'A___N';
```
---
## Query 3: Display the names of employees whose names start with alphabet 'S'
```sql
SELECT ename
FROM employee
WHERE ename LIKE 'S%';
```
---
### Query 4: Display the names of employees whose names end with alphabet 'S'
```sql
SELECT ename
FROM employee
WHERE ename LIKE '%S';
```
---
## Query 5: Display the names of employees working in department number 10, 20, or 40 OR employees working as Clerk, Salesman, or Analyst

```sql
SELECT ename
FROM employee
WHERE deptno IN (10, 20, 40)
   OR job IN ('CLERK', 'SALESMAN', 'ANALYST');
```
---
## Query 6: Display employee number and names for employees who earn commission
```sql
SELECT empno, ename
FROM employee
WHERE comm IS NOT NULL
  AND comm > 0;
```
---
## Query 7: Display employee number and total salary for each employee
```sql
SELECT empno, (sal + IFNULL(comm, 0)) AS total_salary
FROM employee;
```
---
## Query 8: Display employee number and annual salary for each employee
```sql
SELECT empno, (sal * 12) AS annual_salary
FROM employee;
```
---
## Query 9: Display the names of all employees working as Clerks and drawing a salary more than 3,000
```sql
SELECT ename
FROM employee
WHERE job = 'CLERK'
  AND sal > 3000;
```
---
## Query 10: Display the names of employees working as Clerk, Salesman, or Analyst and drawing a salary more than 3,000
```sql
SELECT ename
FROM employee
WHERE job IN ('CLERK', 'SALESMAN', 'ANALYST')
  AND sal > 3000;
```
---