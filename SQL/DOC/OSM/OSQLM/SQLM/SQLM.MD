
---

###### [MUM](https://github.com/ttltrk/PRG/blob/master/MUM.MD) - [M](https://github.com/ttltrk/ELSE/blob/master/M/M.MD) || [PY](https://github.com/ttltrk/PRG/blob/master/PY/DOC/PYF/PYF.MD) - [UX](https://github.com/ttltrk/ELSE/blob/master/M/UX/UX.MD) - [Tools](https://github.com/ttltrk/ELSE/blob/master/M/TOOLS/TOOLS.MD) - [ENG](https://github.com/ttltrk/ELSE/blob/master/LAN/ENG/LE.MD)

---

<h3 id='^'>SQL</h3>

---

[w3schools](https://www.w3schools.com/sql/)

---

* <a href='#SELECT'>SELECT</a>
* <a href='#SELECTDISTINCT'>SELECT DISTINCT</a>
* <a href='#WHERE'>WHERE</a>
* <a href='#ANDORNOT'>AND, OR, NOT</a>
* <a href='#ORDERBY'>ORDER BY</a>
* <a href='#INSERTINTO'>INSERT INTO</a>
* <a href='#NULLVALUES'>NULL VALUES</a>
* <a href='#UPDATE'>UPDATE</a>
* <a href='#DELETE'>DELETE</a>
* <a href='#SELECTTOP'>SELECT TOP</a>
* <a href='#MINMAX'>MIN and MAX</a>
* <a href='#COUNTAVGSUM'>COUNT, AVG, SUM</a>
* <a href='#LIKE'>LIKE</a>
* <a href='#WILDCARDS'>WILDCARDS</a>
* <a href='#IN'>IN</a>
* <a href='#BETWEEN'>BETWEEN</a>
* <a href='#ALIASES'>ALIASES</a>
* <a href='#JOINS'>JOINS</a>
* <a href='#INNERJOIN'>INNER JOIN</a>
* <a href='#LEFTJOIN'>LEFT JOIN</a>
* <a href='#RIGHTJOIN'>RIGHT JOIN</a>
* <a href='#FULLJOIN'>FULL JOIN</a>
* <a href='#SELFJOIN'>SELF JOIN</a>
* <a href='#UNION'>UNION</a>
* <a href='#GROUPBY'>GROUP BY</a>
* <a href='#HAVING'>HAVING</a>
* <a href='#EXISTS'>EXISTS</a>
* <a href='#ANYALL'>ANY, ALL</a>
* <a href='#SELECTINTO'>SELECT INTO</a>
* <a href='#INSINTSEL'>INSERT INTO SELECT</a>
* <a href='#CASE'>CASE</a>
* <a href='#NULL'>NULL FUNCTIONS</a>
* <a href='#STOPRO'>STORED PROCEDURES</a>
* <a href='#COMMENT'>COMMENTS</a>
* <a href='#CREATEDB'>CREATE DB</a>
* <a href='#DROPDB'>DROP DB</a>
* <a href='#BACKUPDB'>BACKUP DB</a>
* <a href='#CREATETABLE'>CREATE TABLE</a>
* <a href='#DROPTABLE'>DROP TABLE</a>
* <a href='#ALTERTABLE'>ALTER TABLE</a>
* <a href='#CONSTRAINTS'>CONSTRAINTS</a>
* <a href='#NOTNULL'>NOT NULL</a>
* <a href='#UNIQUE'>UNIQUE</a>
* <a href='#PRIMARYKEY'>PRIMARY KEY</a>
* <a href='#FOREIGNKEY'>FOREIGN KEY</a>
* <a href='#CHECK'>CHECK</a>
* <a href='#DEFAULT'>DEFAULT</a>
* <a href='#INDEX'>INDEX</a>
* <a href='#AUTOINCREMENT'>AUTO INCREMENT</a>
* <a href='#DATES'>DATES</a>
* <a href='#VIEWS'>VIEWS</a>
* <a href='#INJENCTION'>INJENCTION</a>
* <a href='#HOSTING'>HOSTING</a>

---

<h3 id='SELECT'>SELECT</h3>

```sql
SELECT column1, column2, ...
FROM table_name;
```

<a href='#^'>^^^</a>

```sql
SELECT CustomerName, City FROM Customers;
```

<a href='#^'>^^^</a>

```sql
SELECT * FROM Employees;

PERSONID	LASTNAME	FIRSTNAME	ADDRESS	CITY	    SALARY	COMPANYID
2	        Big	        Bob	        Main str. Norway	1200	4
3	        Nuttall	    Ben	        Raspberry Pi str US	1900	3
6	        Smog	    Smig	    w str	Norway	    4900	2
1	        Doe	        John	    Main str.	Norway	1000	1
5	        ball	    zo	        str str	la	        2900	2
4	        trk	        ttl	        TNO str	SVK	        1900	5
```

<a href='#^'>^^^</a>

---

<h3 id='SELECTDISTINCT'>SELECT DISTINCT</h3>

The SELECT DISTINCT statement is used to return only distinct (different) values.

```sql
SELECT DISTINCT column1, column2, ...
FROM table_name;
```

<a href='#^'>^^^</a>

```sql
SELECT DISTINCT Country FROM Customers;
```

<a href='#^'>^^^</a>

```sql
SELECT COUNT(DISTINCT Country) FROM Customers;
```

<a href='#^'>^^^</a>

```sql
SELECT Count(*) AS DistinctCountries
FROM (SELECT DISTINCT Country FROM Customers);
```

<a href='#^'>^^^</a>

---

<h3 id='WHERE'>WHERE</h3>

```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```

<a href='#^'>^^^</a>

```sql
SELECT * FROM Customers
WHERE Country='Mexico';
```

<a href='#^'>^^^</a>

```sql
SELECT * FROM Customers
WHERE CustomerID=1;
```

<a href='#^'>^^^</a>

```sql
=	      
Equal

<>	    
Not equal. Note: In some versions of SQL this operator may be written as !=

>	      
Greater than

<	      
Less than

>=	    
Greater than or equal

<=	    
Less than or equal

BETWEEN	
Between an inclusive range

LIKE	  
Search for a pattern

IN	    
To specify multiple possible values for a column
```

<a href='#^'>^^^</a>

---

<h3 id='ANDORNOT'>AND, OR, NOT</h3>

```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition1 AND condition2 AND condition3 ...;

SELECT column1, column2, ...
FROM table_name
WHERE condition1 OR condition2 OR condition3 ...;

SELECT column1, column2, ...
FROM table_name
WHERE NOT condition;
```

<a href='#^'>^^^</a>

```sql
SELECT * FROM Customers
WHERE Country='Germany' AND City='Berlin';
```

<a href='#^'>^^^</a>

```sql
SELECT * FROM Customers
WHERE City='Berlin' OR City='München';
```

<a href='#^'>^^^</a>

```sql
SELECT * FROM Customers
WHERE NOT Country='Germany';
```

<a href='#^'>^^^</a>

```sql
SELECT * FROM Customers
WHERE Country='Germany' AND (City='Berlin' OR City='München');
```

<a href='#^'>^^^</a>

```sql
SELECT * FROM Customers
WHERE NOT Country='Germany' AND NOT Country='USA';
```

<a href='#^'>^^^</a>

---

<h3 id='ORDERBY'>ORDER BY</h3>

```sql
SELECT column1, column2, ...
FROM table_name
ORDER BY column1, column2, ... ASC|DESC;
```

<a href='#^'>^^^</a>

```sql
SELECT * FROM Customers
ORDER BY Country;
```

<a href='#^'>^^^</a>

```sql
SELECT * FROM Customers
ORDER BY Country DESC;
```

<a href='#^'>^^^</a>

```sql
SELECT * FROM Customers
ORDER BY Country, CustomerName;
```

<a href='#^'>^^^</a>

```sql
SELECT * FROM Customers
ORDER BY Country ASC, CustomerName DESC;
```

<a href='#^'>^^^</a>

---

<h3 id='INSERTINTO'>INSERT INTO</h3>

```sql
INSERT INTO table_name (column1, column2, column3, ...)
VALUES (value1, value2, value3, ...);

INSERT INTO table_name
VALUES (value1, value2, value3, ...);
```

<a href='#^'>^^^</a>

```sql
INSERT INTO Customers (CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES ('Cardinal', 'Tom B. Erichsen', 'Skagen 21', 'Stavanger', '4006', 'Norway');
```

<a href='#^'>^^^</a>

```sql
INSERT INTO Customers (CustomerName, City, Country)
VALUES ('Cardinal', 'Stavanger', 'Norway');
```

<a href='#^'>^^^</a>

---

Inserting multiple rows in a single SQL query

```sql
INSERT INTO tbl_name (a,b,c) VALUES(1,2,3),(4,5,6),(7,8,9);
```

```sql
INSERT INTO MyTable 
    ( Column1, Column2, Column3 )
VALUES 
    ('John', 123, 'Lloyds Office'), 
    ('Jane', 124, 'Lloyds Office'), 
    ('Billy', 125, 'London Office'),
    ('Miranda', 126, 'Bristol Office');
```

<a href='#^'>^^^</a>

---

```sql
SELECT * 
FROM trk_test;

INSERT INTO trk_test 
VALUES ('4','king','bbe','hemp','ams');

INSERT INTO trk_test 
VALUES ('5','petofi','alex','var','bp');

>>>
1	"trk"	"ttl"	"Hlavna 5"	"TNO"
2	"doe"	"jon"	"CA"	"GS"
3	"ewong"	"samatha"	"SFR"	"Dallas"
4	"king"	"bbe"	"hemp"	"ams"
5	"petofi"	"alex"	"var"	"bp"
>>>
```

<h3 id='NULLVALUES'>NULL VALUES</h3>

<a href='#^'>^^^</a>

---

<h3 id='UPDATE'>UPDATE</h3>

```sql
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;
```

<a href='#^'>^^^</a>

```sql
UPDATE Customers
SET ContactName = 'Alfred Schmidt', City= 'Frankfurt'
WHERE CustomerID = 1;
```

<a href='#^'>^^^</a>

```sql
UPDATE Customers
SET ContactName='Juan'
WHERE Country='Mexico';
```

<a href='#^'>^^^</a>

---

<h3 id='CREATETABLE'>CREATE TABLE</h3>

```sql
CREATE TABLE trk (
    PersonID int,
    LastName varchar(255),
    FirstName varchar(255),
    Address varchar(255),
    City varchar(255) 
);
```

---

Create, Insert and Select table

```sql
CREATE TABLE trk (
    PersonID int,
    LastName varchar(255),
    FirstName varchar(255),
    Address varchar(255),
    City varchar(255) 
);

INSERT INTO trk (PersonID , LastName , FirstName , Address , City)
VALUES (01, 'Doe', 'John', 'Main str.', 'Norway');

select * from trk
```

<a href='#^'>^^^</a>

---

<h3 id=''></h3>

<a href='#^'>^^^</a>

---

<h3 id=''></h3>

<a href='#^'>^^^</a>

---

<h3 id=''></h3>

<a href='#^'>^^^</a>

---

<h3 id=''></h3>

<a href='#^'>^^^</a>

---
