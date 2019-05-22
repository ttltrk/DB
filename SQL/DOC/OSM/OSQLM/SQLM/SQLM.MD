
---

###### [改善](https://github.com/ttltrk/0C/blob/master/README.MD) - [.co.](https://github.com/ttltrk/PRG/blob/master/CODING.MD) - [manuals](https://github.com/ttltrk/PRG/blob/master/MAN.MD)

###### [MUM](https://github.com/ttltrk/PRG/blob/master/MUM.MD) - [M](https://github.com/ttltrk/ELSE/blob/master/M/M.MD) || [PY](https://github.com/ttltrk/PRG/blob/master/PY/DOC/PYF/PYF.MD) - [SQL](https://github.com/ttltrk/DB/blob/master/SQL/DOC/OSM/OSQLM/SQLM/SQLM.MD) - [UX](https://github.com/ttltrk/ELSE/blob/master/M/UX/UX.MD) || [ENG](https://github.com/ttltrk/ELSE/blob/master/LAN/ENG/LE.MD) - [DE](https://github.com/ttltrk/ELSE/blob/master/LAN/GER/DUO_GER.MD) - [SP](https://github.com/ttltrk/ELSE/blob/master/LAN/SP/SP.MD) || [Tools](https://github.com/ttltrk/ELSE/blob/master/M/TOOLS/TOOLS.MD)

---

<h3 id='^'>SQL</h3>

---

```sql
--SELECT * FROM
SELECT * FROM emp;
SELECT id, lastname FROM emp; 

--SELECT DISTINCT
SELECT DISTINCT Country FROM Customers; 
SELECT COUNT(DISTINCT Country) FROM Customers;
SELECT COUNT(*) AS DistinctCountries FROM (SELECT DISTINCT Country FROM Customers);

--WHERE
SELECT * FROM Customers WHERE Country='Mexico';
SELECT * FROM Customers WHERE CustomerID=1;

--AND, OR, NOT
SELECT * FROM Customers WHERE Country='Germany' AND City='Berlin';
SELECT * FROM Customers WHERE City='Berlin' OR City='München';
SELECT * FROM Customers WHERE NOT Country='Germany';
SELECT * FROM Customers WHERE Country='Germany' AND (City='Berlin' OR City='München');
SELECT * FROM Customers WHERE NOT Country='Germany' AND NOT Country='USA';

--ORDER BY
SELECT * FROM Customers ORDER BY Country;
SELECT * FROM Customers ORDER BY Country DESC;
SELECT * FROM Customers ORDER BY Country, CustomerName;
SELECT * FROM Customers ORDER BY Country ASC, CustomerName DESC;

--INSERT INTO
INSERT INTO Customers (CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES ('Cardinal', 'Tom B. Erichsen', 'Skagen 21', 'Stavanger', '4006', 'Norway');

--UPDATE
UPDATE Customers SET ContactName = 'Alfred Schmidt', City= 'Frankfurt' WHERE CustomerID = 1;
UPDATE Customers SET ContactName='Juan' WHERE Country='Mexico';
```

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

<h3 id='altertable'>ALTER TABLE</h3>

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
