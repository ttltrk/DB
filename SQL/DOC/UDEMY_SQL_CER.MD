
[The Complete Udemy SQL Certification Course](https://www.udemy.com/the-complete-oracle-sql-certification-course/learn/v4/content)
======

### Database Basics
  * Oracle Database Introduction & Basics of Tables
  * Setting Up the SQL Development Environment
  
### Single Table Queries
  *
  *
  *
  *
  *

### Section 3

### Section 4

### Section 5

### Section 6

Database Basics
------

#### Oracle Database Introduction & Basics of Tables

#### Setting Up the SQL Development Environment

Single Table Queries
------

#### Retrieving Data Using the SELECT Clause

#### Using the WHERE Clause

#### Using Operators in the WHERE Clause

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

#### Combining WHERE, AND & OR with Operators

```SQL
--

```
