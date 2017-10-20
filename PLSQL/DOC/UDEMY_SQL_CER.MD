[The Complete Udemy SQL Certification Course](https://www.udemy.com/the-complete-oracle-sql-certification-course/learn/v4/content)
======

Section 1

Section 2

Section 3

Section 4

Section 5

Section 6

Database Basics
------

#### Oracle Database Introduction & Basics of Tables

#### Setting Up the SQL Development Environment

Single Table Queries
------

#### Retrieving Data Using the SELECT Clause

### Using the WHERE Clause

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
