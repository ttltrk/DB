
[The Complete Oracle SQL Certification Course](https://www.udemy.com/the-complete-oracle-sql-certification-course/learn/v4/content)
======

### Database Basics
  * <a href='#1'>Oracle Database Introduction & Basics of Tables</a>
  * <a href='#2'>Setting Up the SQL Development Environment</a>
  
### Single Table Queries
  * <a href='#3'>Retrieving Data Using the SELECT Clause</a>
  * <a href='#4'>Using the WHERE Clause</a>
  * <a href='#5'>Using Operators in the WHERE Clause</a>
  * <a href='#6'>Combining WHERE, AND & OR with Operators</a>
  * <a href='#7'>Query Filtering Continued BETWEEN, IN and NULL</a>

### Section 3

### Section 4

### Section 5

### Section 6

Database Basics
------

#### <h4 id='1'>Oracle Database Introduction & Basics of Tables</h4>

#### <h4 id='2'>Setting Up the SQL Development Environment</h4>

Single Table Queries
------

#### <h4 id='3'>Retrieving Data Using the SELECT Clause</h4>

#### <h4 id='4'>Using the WHERE Clause</h4>

#### <h4 id='5'>Using Operators in the WHERE Clause</h4>

WHERE

```SQL
--List Out, all the managers from EMP
SELECT * FROM EMP
WHERE JOB = 'MANAGER';
```

```SQL
--List Out, all the jobs without MANAGER from EMP
SELECT * FROM EMP
WHERE JOB != 'MANAGER';
```

```SQL
--List Out, all the salesman with salary 1500 from EMP
SELECT * FROM EMP
WHERE JOB = 'SALESMAN'
AND SAL = 1500;
```

```SQL
--List Out, all the salesman with salary less than 2500 from EMP
SELECT * FROM EMP
WHERE JOB = 'SALESMAN'
AND SAL < 2500;
```

```SQL
--List Out, all the salesman with salary less than or equal to 3000 from EMP
SELECT * FROM EMP
WHERE JOB = 'SALESMAN'
AND SAL <= 3000;
```

```SQL
--Return the employees who have a comission greater than their salary
SELECT * FROM EMP
WHERE SAL < COMM;
```

```SQL
--Get all employees that are not managers and have sal greater than 2500 and also work in dep no#20
SELECT * FROM EMP
WHERE JOB != 'MANAGERS' 
AND SAL > 2500
AND DEPTNO = 20;
```

#### <h4 id='6'>Combining WHERE, AND & OR with Operators</h4>

OR

```SQL
--Get all employees that are clerks and salesmans.
SELECT * FROM EMP
WHERE JOB='CLERK'
OR JOB='SALESMAN';
```

AND

```SQL
--Get the names of those employees that are not managers nor salesman and have a salary greater than or
--equal to 2000
SELECT * FROM EMP
WHERE JOB != 'MANAGER'
AND JOB !='SALESMAN'
AND SAL >= 2000;
```
#### <h4 id='7'>Query Filtering Continued BETWEEN, IN and NULL</h4>

IN

```SQL
--Get the names of the employees that works in Dallas and in Chicago
SELECT ename, hiredate, deptno FROM EMP
WHERE DEPTNO IN (20, 30);
```

```SQL
--get the mentioned names
SELECT ename, hiredate
FROM EMP
WHERE ENAME IN ('FORD', 'SMITH');
```

NOT IN

```SQL
get all the names without the selected ones
SELECT ename, hiredate
FROM EMP
WHERE ENAME NOT IN ('FORD', 'SMITH');
```

BETWEEN

```SQL
--between the selected range
SELECT * FROM EMP
WHERE hiredate 
BETWEEN '05/01/1981' AND '01/12/1983';
```

NOT BETWEEN

```SQL
SELECT * FROM EMP
WHERE SAL 
NOT BETWEEN 1000 AND 2000;
```

NULL

```SQL
--records with no data
SELECT * FROM EMP
WHERE COMM IS NULL;
```

NOT NULL

```SQL
SELECT * FROM EMP
WHERE COMM IS NOT NULL;
```







