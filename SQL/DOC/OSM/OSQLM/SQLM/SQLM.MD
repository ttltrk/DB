
---

###### [改善](https://github.com/ttltrk/0C/blob/master/README.MD) - [.co.](https://github.com/ttltrk/PRG/blob/master/CODING.MD) - [manuals](https://github.com/ttltrk/PRG/blob/master/MAN.MD)

###### [MUM](https://github.com/ttltrk/PRG/blob/master/MUM.MD) - [M](https://github.com/ttltrk/ELSE/blob/master/M/M.MD) || [PY](https://github.com/ttltrk/PRG/blob/master/PY/DOC/PYF/PYF.MD) - [SQL](https://github.com/ttltrk/DB/blob/master/SQL/DOC/OSM/OSQLM/SQLM/SQLM.MD) - [UX](https://github.com/ttltrk/ELSE/blob/master/M/UX/UX.MD) || [ENG](https://github.com/ttltrk/ELSE/blob/master/LAN/ENG/LE.MD) - [DE](https://github.com/ttltrk/ELSE/blob/master/LAN/GER/DUO_GER.MD) - [SP](https://github.com/ttltrk/ELSE/blob/master/LAN/SP/SP.MD) || [Tools](https://github.com/ttltrk/ELSE/blob/master/M/TOOLS/TOOLS.MD)

---

<h3 id='^'>SQL</h3>

---

* <a href='#select'>select</a></br>
* <a href='#selectdist'>select distinct</a></br>
* <a href='#where'>where</a></br>
* <a href='#orderby'>order by</a></br>
* <a href='#andornot'>and, or, not</a></br>
* <a href='#limit'>limit</a></br>
* <a href='#minmax'>min, max</a></br>
* <a href='#countavgsum'>count, avg, sum</a></br>
* <a href='#between'>between</a></br>
* <a href='#in'>in</a></br>
* <a href='#like'>like</a></br>
* <a href='#insert'>insert</a></br>
* <a href='#update'>update</a></br>
* <a href='#delete'>delete</a></br>
* <a href='#create'>create</a></br>
* <a href='#alter'>alter</a></br>

---

<h3 id='select'>select</h3>

```sql
SELECT * FROM emp;
SELECT id, lastname FROM emp; 

>>>
personid|lastname|firstname|address |city   |
--------|--------|---------|--------|-------|
       1|trk     |ttl      |Hlavna 5|TNO    |
       2|doe     |jon      |CA      |GS     |
       3|ewong   |samatha  |SFR     |Dallas |
       6|kawhi   |leo      |canada  |toronto|
       4|bbking  |bbe      |hemp    |ams    |
       5|petofi  |alex     |var     |BP     |
>>>
```

<a href='#^'>^^^</a>

---

<h3 id='selectdist'>select distinct</h3>

```sql
SELECT DISTINCT Country FROM Customers; 
SELECT COUNT(DISTINCT Country) FROM Customers;
SELECT COUNT(*) AS DistinctCountries FROM (SELECT DISTINCT Country FROM Customers);
```

<a href='#^'>^^^</a>

---

<h3 id='where'>where</h3>

```sql
SELECT * FROM Customers WHERE Country='Mexico';
SELECT * FROM Customers WHERE CustomerID=1;
```

<a href='#^'>^^^</a>

---

<h3 id='orderby'>order by</h3>

```sql
SELECT * FROM Customers ORDER BY Country;
SELECT * FROM Customers ORDER BY Country DESC;
SELECT * FROM Customers ORDER BY Country, CustomerName;
SELECT * FROM Customers ORDER BY Country ASC, CustomerName DESC;
```

<a href='#^'>^^^</a>

---

<h3 id='andornot'>and, or, not</h3>

```sql
SELECT * FROM Customers WHERE Country='Germany' AND City='Berlin';
SELECT * FROM Customers WHERE City='Berlin' OR City='München';
SELECT * FROM Customers WHERE NOT Country='Germany';
SELECT * FROM Customers WHERE Country='Germany' AND (City='Berlin' OR City='München');
SELECT * FROM Customers WHERE NOT Country='Germany' AND NOT Country='USA';
```

<a href='#^'>^^^</a>

---

<h3 id='limit'>limit</h3>

```sql
SELECT * FROM Customers LIMIT 3;
```

<a href='#^'>^^^</a>

---

<h3 id='minmax'>min, max</h3>

```sql
SELECT MIN(Price) AS SmallestPrice FROM Products;
SELECT MAX(Price) AS LargestPrice FROM Products;
```

<a href='#^'>^^^</a>

---

<h3 id='countavgsum'>count, avg, sum</h3>

```sql
SELECT COUNT(ProductID) FROM Products;
SELECT COUNT(DISTINCT ProductID) FROM Products;
SELECT AVG(Price) FROM Products;
SELECT SUM(Quantity) FROM OrderDetails;
```

<a href='#^'>^^^</a>

---

<h3 id='between'>between</h3>

```sql
SELECT customer_id, amount
FROM payment
WHERE amount BETWEEN 8 AND 9;
```

```sql
SELECT amount, payment_date
FROM payment
WHERE payment_date BETWEEN '2007-02-07' AND '2007-02-15';
```

<a href='#^'>^^^</a>

---

<h3 id='in'>in</h3>

```sql
SELECT customer_id, rental_id, return_date
FROM rental
WHERE customer_id IN (1,2)
ORDER BY return_date DESC;
```

```sql
SELECT customer_id, rental_id, return_date
FROM rental
WHERE customer_id IN (1,2,7,21)
ORDER BY return_date DESC;
```

```sql
SELECT customer_id, rental_id, return_date
FROM rental
WHERE customer_id NOT IN (1,2)
ORDER BY return_date DESC;
```

<a href='#^'>^^^</a>

---

<h3 id='like'>like</h3>

```sql
SELECT first_name, last_name
FROM customer
WHERE first_name LIKE 'Jen%';
```

```sql
SELECT first_name, last_name
FROM customer
WHERE first_name NOT LIKE 'Jen%';
```

```sql
SELECT first_name, last_name
FROM customer
WHERE first_name LIKE '%em%';
```

<a href='#^'>^^^</a>

---

<h3 id='insert'>insert</h3>

```sql
INSERT INTO table_name (column1, column2, column3, ...)
VALUES (value1, value2, value3, ...);

INSERT INTO table_name
VALUES (value1, value2, value3, ...);
```

```sql
INSERT INTO Customers (CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES ('Cardinal', 'Tom B. Erichsen', 'Skagen 21', 'Stavanger', '4006', 'Norway');
```

```sql
INSERT INTO Customers (CustomerName, City, Country)
VALUES ('Cardinal', 'Stavanger', 'Norway');
```

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

```sql
INSERT INTO Customers (CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES ('Cardinal', 'Tom B. Erichsen', 'Skagen 21', 'Stavanger', '4006', 'Norway');
```

<a href='#^'>^^^</a>

---

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

```sql
UPDATE Customers SET ContactName = 'Alfred Schmidt', City= 'Frankfurt' WHERE CustomerID = 1;
UPDATE Customers SET ContactName='Juan' WHERE Country='Mexico';
```

<a href='#^'>^^^</a>

---

<h3 id='delete'>delete</h3>

```sql
DELETE FROM Customers WHERE CustomerName='Alfreds Futterkiste';
DELETE FROM Customers;
```

<a href='#^'>^^^</a>

---

<h3 id='create'>create</h3>

create table

```sql
CREATE TABLE trk (
    PersonID int,
    LastName varchar(255),
    FirstName varchar(255),
    Address varchar(255),
    City varchar(255) 
);
```

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

<h3 id='alter'>alter</h3>

alter table

```sql
--How to rename column name from department to dep

ALTER TABLE trk_test_02
RENAME COLUMN department TO dep;
```

```sql
--add new column to the table

ALTER TABLE trk_test_02
ADD city varchar(255);
```

```sql
--change the table name from trk_test to trk_test_01

ALTER TABLE trk_test
  RENAME TO trk_test_01;
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
