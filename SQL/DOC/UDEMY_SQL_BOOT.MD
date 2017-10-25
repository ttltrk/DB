
[The Complete SQL Bootcamp](https://www.udemy.com/the-complete-sql-bootcamp/learn/v4/overview)
========

### Course Introduction
  * <a href='#1'>Introduction</a>
  * <a href='#2'>Course Curriculum Overview</a>
  * <a href='#3'>Overview of Databases</a>
  * <a href='#4'>Course FAQs</a>
  * <a href='#5'>Time to get your Computer Set-Up!</a>
  * <a href='#6'>Setting Up with pgAdmin 4</a>
  * <a href='#7'>Installation Notes</a>

### PostGreSQL Installation (Mac)
  * <a href='#8'>Mac OS X - Quick Note</a>
  * <a href='#9'>Mac OS Installation</a>
  * <a href='#10'>Mac Sample Database Download</a>
  * <a href='#11'>Mac Database Set-up</a>
  * <a href='#12'>Review of Set-up</a>

### PostGreSQL Installation (Win)
  * <a href='#13'>Windows - Quick Note</a>
  * <a href='#14'>Windows Installation</a>
  * <a href='#15'>Sample Database Download</a>
  * <a href='#16'>Windows Command Line Installation Lecture</a>
  
### Databases and Tables
  * <a href='#17'>Databases and Tables Overview</a>
  * <a href='#18'>Creating and restoring a Database</a>
  * <a href='#19'>Overview of Challenges!</a>
  * <a href='#20'>Challenge: Restore a Database!</a>
  * <a href='#21'>Restoring a Table Schema</a>
  * <a href='#22'>Challenge: Restore a Table Schema!</a>
  * <a href='#23'>Review of Section</a>

### SQL Statement Fundamentals
  * <a href='#24'>SQL Cheat Sheet</a>
  * <a href='#25'>SQL Statement Fundamentals</a>
  * <a href='#26'>SELECT Statement</a>
  * <a href='#27'>Challenge: SELECT task</a>
  * <a href='#28'>SELECT DISTINCT</a>
  * <a href='#29'>Challenge: SELECT DISTINCT</a>
  * <a href='#30'>SELECT WHERE</a>
  * <a href='#31'>Challenge: SELECT WHERE</a>
  * <a href='#32'>COUNT</a>
  * <a href='#33'>LIMIT</a>
  * <a href='#34'>ORDER BY</a>
  * <a href='#35'>Challenge: ORDER BY</a>
  * <a href='#36'>BETWEEN</a>
  * <a href='#37'>IN</a>
  * <a href='#38'>LIKE</a>
  * <a href='#39'>General Challenge 1</a>

### GROUP BY Statement
  * <a href='#40'>MIN MAX SUM and AVG</a>
  * <a href='#41'>GROUP BY</a>
  * <a href='#42'>Challenge: GROUP BY</a>
  * <a href='#43'>HAVING</a>
  * <a href='#44'>Quick Note</a>
  * <a href='#45'>Challenge: HAVING</a>

### Assessment Test 1
  * Overview of Assessment Test 1
  * Assessment Test 1
  * Solutions to Assessment Test 1

### JOINS
  * Overview of JOINS
  * AS Statement
  * Overview of Inner Join
  * Examples of Inner Joins
  * Overview of Join types
  * Example of Outer Joins
  * Union
  * Join Challenges

### Advanced SQL Commands
  * Overview of Advanced SQL Commands
  * Timestamps and Extract
  * Mathematical Functions
  * String Function and Operators
  * SubQuery
  * Self-Join

### Assessment Test 2
  * Assessment Test 2 Overview
  * Assessment Test 2
  * Solutions to Assessment Test 2

### Creating Databases and Tables
  * Overview of Section
  * Data Types
  * Primary Keys and Foreign Keys
  * Resource for Create Table Code
  * Note on Constrains
  * Create Table
  * Challenge: Create Table
  * Challenge: Create Table - SOLUTION
  * Insert
  * Update
  * Delete
  * Alter Table
  * Drop Table
  * CHECK Constraint
  * NOT NULL Constraint
  * UNIQUE Constraint

### Assessment Test 3
  * Assessment Test 3
  * Solutions to Assessment Test 3

### Extra Views
  * Views

### Extra PostGreSQL with Python
  * Overview of Python and PostGreSQL
  * Psycopg2 Example Usage
  * Psycopg2 Resources

### Bonus Offers
  * Bonus Offers

Course Introduction
------

#### <h4 id='1'>Introduction</h4>
  
#### <h4 id='2'>Course Curriculum Overview</h4>
  
#### <h4 id='3'>Overview of Databases</h4>
  
#### <h4 id='4'>Course FAQs</h4>
  
#### <h4 id='5'>Time to get your Computer Set-Up!</h4>
  
#### <h4 id='6'>Setting Up with pgAdmin 4</h4>
  
#### <h4 id='7'>Installation Notes</h4>

PostGreSQL Installation (Mac)
------

#### <h4 id='8'>Mac OS X - Quick Note</h4>

#### <h4 id='9'>Mac OS Installation</h4>

#### <h4 id='10'>Mac Sample Database Download</h4>

#### <h4 id='11'>Mac Database Set-up</h4>

#### <h4 id='12'>Review of Set-up</h4>

PostGreSQL Installation (Win)
------

#### <h4 id='13'>Windows - Quick Note</h4>

#### <h4 id='14'>Windows Installation</h4>

#### <h4 id='15'>Sample Database Download</h4>

#### <h4 id='16'>Windows Command Line Installation Lecture</h4>

Databases and Tables
------

#### <h4 id='17'>Databases and Tables Overview</h4>

#### <h4 id='18'>Creating and restoring a Database</h4>

create

```SQL
	CREATE DATABASE testpg
    WITH 
    OWNER = postgres
    ENCODING = 'UTF8'
    CONNECTION LIMIT = -1;
 ```
 
 restore

```
	right click >>> restore >>> upload the .tar file and GO
```

delete

```
	right click >>> delete/drop
```

#### <h4 id='19'>Overview of Challenges!</h4>

#### <h4 id='20'>Challenge: Restore a Database!</h4>

#### <h4 id='21'>Restoring a Table Schema</h4>

To the new DB

```
newdb >>> restore >>> find the .tar file >>> restore options >>> only schema YES >>> restore >>> refresh
```

To the old DB

```
olddb >>> restore >>> find the .tar file >>> restore options >>> only schema YES >>> clean before restore YES 
>>> restore >>> refresh
```

#### <h4 id='22'>Challenge: Restore a Table Schema!</h4>

#### <h4 id='23'>Review of Section</h4>

SQL Statement Fundamentals
------

#### <h4 id='24'>SQL Cheat Sheet</h4>

#### <h4 id='25'>SQL Statement Fundamentals</h4>

#### <h4 id='26'>SELECT Statement</h4>

```SQL
SELECT column1, column2 FROM table_name;
```

```SQL
--get all the value from the table actor
SELECT * FROM actor;
```

```SQL
--get all the first_name and all the last_name from the table actor
SELECT first_name, last_name FROM actor;
```

#### <h4 id='27'>Challenge: SELECT task</h4>

#### <h4 id='28'>SELECT DISTINCT</h4>

```SQL
SELECT DISTINCT rental_rate FROM film;
```

#### <h4 id='29'>Challenge: SELECT DISTINCT</h4>

#### <h4 id='30'>SELECT WHERE</h4>

```SQL
-- get all the customer (Jamie) 
SELECT * 
FROM customer
WHERE first_name = 'Jamie';
```

```SQL
SELECT * 
FROM customer
WHERE first_name = 'Jamie' AND last_name = 'Waugh';
```

```SQL
SELECT customer_id, amount, payment_date 
FROM payment
WHERE amount <= 1 
OR amount >= 8;
```

#### <h4 id='31'>Challenge: SELECT WHERE</h4>

#### <h4 id='32'>COUNT</h4>

```SQL
--count the the rows in the payment
SELECT COUNT(*)
FROM payment;
```

```SQL
SELECT COUNT(DISTINCT amount)
FROM payment;
```

#### <h4 id='33'>LIMIT</h4>

```SQL
--we will receive only 3 rows
SELECT *
FROM customer
LIMIT 3;
```

#### <h4 id='34'>ORDER BY</h4>

```SQL
SELECT first_name, last_name
FROM customer
ORDER BY first_name ASC;
```

#### <h4 id='35'>Challenge: ORDER BY</h4>

#### <h4 id='36'>BETWEEN</h4>

```SQL
SELECT customer_id, amount
FROM payment
WHERE amount BETWEEN 8 AND 9;
```

```SQL
SELECT amount, payment_date
FROM payment
WHERE payment_date BETWEEN '2007-02-07' AND '2007-02-15';
```

#### <h4 id='37'>IN</h4>

```SQL
SELECT customer_id, rental_id, return_date
FROM rental
WHERE customer_id IN (1,2)
ORDER BY return_date DESC;
```

```SQL
SELECT customer_id, rental_id, return_date
FROM rental
WHERE customer_id IN (1,2,7,21)
ORDER BY return_date DESC;
```

```SQL
SELECT customer_id, rental_id, return_date
FROM rental
WHERE customer_id NOT IN (1,2)
ORDER BY return_date DESC;
```

#### <h4 id='38'>LIKE</h4>

```SQL
SELECT first_name, last_name
FROM customer
WHERE first_name LIKE 'Jen%';
```

```SQL
SELECT first_name, last_name
FROM customer
WHERE first_name NOT LIKE 'Jen%';
```

```SQL
SELECT first_name, last_name
FROM customer
WHERE first_name LIKE '%em%';
```

#### <h4 id='39'>General Challenge 1</h4>

GROUP BY Statement
------

#### <h4 id='40'>MIN MAX SUM and AVG</h4>

#### <h4 id='41'>GROUP BY</h4>

#### <h4 id='42'>Challenge: GROUP BY</h4>

#### <h4 id='43'>HAVING</h4>

#### <h4 id='44'>Quick Note</h4>

#### <h4 id='45'>Challenge: HAVING</h4>

Assessment Test 1
------

JOINS
------

Advanced SQL Commands
------

Assessment Test 2
------

Creating Databases and Tables
------

Assessment Test 2
------

Extra Views
------

Extra PostGreSQL with Python
------

Bonus Offers
------
