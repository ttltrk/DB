
---

###### [改善](https://github.com/ttltrk/0C/blob/master/README.MD) - [.co.](https://github.com/ttltrk/PRG/blob/master/CODING.MD) - [manuals](https://github.com/ttltrk/PRG/blob/master/MAN.MD)

###### [PY](https://github.com/ttltrk/PRG/blob/master/PY/DOC/PYF/PYF.MD) - [JV](https://github.com/ttltrk/PRG/blob/master/JAVA/JAVA.MD) - [C](https://github.com/ttltrk/PRG/blob/master/C/C.MD) - [SQL](https://github.com/ttltrk/DB/blob/master/SQL/DOC/OSM/OSQLM/SQLM/SQLM.MD) - [SH](https://github.com/ttltrk/ELSE/blob/master/M/UX/UX.MD) - [PL](https://github.com/ttltrk/PRG/blob/master/PERL/PL.MD) - [DS](https://github.com/ttltrk/ELSE/blob/master/DATA/DS/DS.MD) - [DO](https://github.com/ttltrk/ELSE/blob/master/DOCKER/DOCKER/DOCKER.MD) || [ENG](https://github.com/ttltrk/ELSE/blob/master/LAN/ENG/LE.MD) - [DE](https://github.com/ttltrk/ELSE/blob/master/LAN/GER/DUO_GER.MD) - [SP](https://github.com/ttltrk/ELSE/blob/master/LAN/SP/SP.MD) - [FR](https://github.com/ttltrk/ELSE/blob/master/LAN/FR/FR.MD) - [TR](https://github.com/ttltrk/ELSE/blob/master/LAN/TR/TR.MD) - [LA](https://github.com/ttltrk/ELSE/blob/master/LAN/LATIN/LATIN.MD) - [ESP](https://github.com/ttltrk/ELSE/blob/master/LAN/ESP/ESP.MD) || [Tools](https://github.com/ttltrk/ELSE/blob/master/M/TOOLS/TOOLS.MD)

---

<h3 id='^'>SQL</h3>

---

* <a href='#select'>SELECT</a></br>
* <a href='#selectdist'>SELECT DISTINCT</a></br>
* <a href='#where'>WHERE</a></br>
* <a href='#andornot'>AND, OR, NOT</a></br>
* <a href='#orderby'>ORDER BY</a></br>
* <a href='#limit'>LIMIT</a></br>
* <a href='#minmax'>MIN, MAX</a></br>
* <a href='#countavgsum'>COUNT, AVG, SUM</a></br>
* <a href='#between'>BETWEEN</a></br>
* <a href='#in'>IN</a></br>
* <a href='#like'>LIKE</a></br>
* <a href='#alias'>ALIAS</a></br>
* <a href='#insert'>INSERT</a></br>
* <a href='#update'>UPDATE</a></br>
* <a href='#delete'>DELETE</a></br>
* <a href='#create'>CREATE</a></br>
* <a href='#alter'>ALTER</a></br>
* <a href='#join'>JOIN</a></br>
* <a href='#union'>UNION</a></br>

---

<h3 id='select'>select</h3>

```SQL
SELECT * FROM trk_test_01;

personid|lastname|firstname|address |city   |
--------|--------|---------|--------|-------|
       1|trk     |ttl      |Hlavna 5|TNO    |
       2|doe     |jon      |CA      |GS     |
       3|ewong   |samatha  |SFR     |Dallas |
       6|kawhi   |leo      |canada  |toronto|
       4|bbking  |bbe      |hemp    |ams    |
       5|petofi  |alex     |var     |BP     |
```

```sql       
SELECT * FROM trk_test_02;

systemid|dep       |city|
--------|----------|----|
       1|ITOPS     |BA  |
       2|DEVOPS    |BP  |
       3|HR        |SF  |
       4|MANAGEMENT|LA  |
       5|ITOPS     |BP  |
       6|ITOPS     |LN  |
       7|DEVOPS    |NYC |
```

```sql
SELECT personid, lastname FROM trk_test_01; 

personid|lastname|
--------|--------|
       1|trk     |
       2|doe     |
       3|ewong   |
       6|kawhi   |
       4|bbking  |
       5|petofi  |
```

```sql
SELECT lastname FROM (SELECT * FROM trk_test_01) AS lname --select from select

lastname|
--------|
trk     |
doe     |
ewong   |
kawhi   |
bbking  |
petofi  |
```

<a href='#^'>^^^</a>

---

<h3 id='selectdist'>select distinct</h3>

```sql
SELECT city FROM trk_test_02; 

city|
----|
BA  |
BP  |
SF  |
LA  |
BP  |
LN  |
NYC |
```

```sql
SELECT DISTINCT city FROM trk_test_02; 

city|
----|
LA  |
SF  |
LN  |
BA  |
NYC |
BP  |
```

```sql
SELECT COUNT(DISTINCT city) FROM trk_test_02;

count|
-----|
    6|
```

```sql
SELECT COUNT(city) FROM trk_test_02;

count|
-----|
    7|
```

```sql
--only even numbers
SELECT distinct personid FROM trk_test_01 WHERE Mod(personid,2)=0; 

personid|
--------|
       2|
       4|
       6|
```

```sql
--Write a query to find the difference between the total number of cities 
--and the unique number of cities in the table STATION.
SELECT COUNT(city) - COUNT(DISTINCT city) AS difference FROM trk_test_02;

difference|
----------|
         1|
       
```

<a href='#^'>^^^</a>

---

<h3 id='where'>where</h3>

```sql
SELECT * FROM trk_test_01 WHERE lastname='kawhi';

personid|lastname|firstname|address|city   |
--------|--------|---------|-------|-------|
       6|kawhi   |leo      |canada |toronto|
       
SELECT * FROM trk_test_02 WHERE city='BP';

systemid|dep   |city|
--------|------|----|
       2|DEVOPS|BP  |
       5|ITOPS |BP  |
```

<a href='#^'>^^^</a>

---

<h3 id='andornot'>and, or, not</h3>

```sql
SELECT * FROM trk_test_02;

systemid|dep       |city|
--------|----------|----|
       1|ITOPS     |BA  |
       2|DEVOPS    |BP  |
       3|HR        |SF  |
       4|MANAGEMENT|LA  |
       5|ITOPS     |BP  |
       6|ITOPS     |LN  |
       7|DEVOPS    |NYC |
       
SELECT * FROM trk_test_02 WHERE city='BP' AND dep='DEVOPS';

systemid|dep   |city|
--------|------|----|
       2|DEVOPS|BP  |
       
SELECT * FROM trk_test_02 WHERE city='BP' OR city='BA';

systemid|dep   |city|
--------|------|----|
       1|ITOPS |BA  |
       2|DEVOPS|BP  |
       5|ITOPS |BP  |
       
SELECT * FROM trk_test_02 WHERE NOT city='BP';

systemid|dep       |city|
--------|----------|----|
       1|ITOPS     |BA  |
       3|HR        |SF  |
       4|MANAGEMENT|LA  |
       6|ITOPS     |LN  |
       7|DEVOPS    |NYC |
       
SELECT * FROM trk_test_02 WHERE dep='ITOPS' AND (City='BA' OR City='BP');

systemid|dep  |city|
--------|-----|----|
       1|ITOPS|BA  |
       5|ITOPS|BP  |
       
SELECT * FROM trk_test_02 WHERE NOT city='NYC' AND NOT dep='ITOPS';

systemid|dep       |city|
--------|----------|----|
       2|DEVOPS    |BP  |
       3|HR        |SF  |
       4|MANAGEMENT|LA  |
```

<a href='#^'>^^^</a>

---

<h3 id='orderby'>order by</h3>

```sql
SELECT * FROM trk_test_01 ORDER BY city;

personid|lastname|firstname|address |city   |
--------|--------|---------|--------|-------|
       4|bbking  |bbe      |hemp    |ams    |
       5|petofi  |alex     |var     |BP     |
       3|ewong   |samatha  |SFR     |Dallas |
       2|doe     |jon      |CA      |GS     |
       1|trk     |ttl      |Hlavna 5|TNO    |
       6|kawhi   |leo      |canada  |toronto|
```

```sql
SELECT * FROM trk_test_01 ORDER BY city DESC;

personid|lastname|firstname|address |city   |
--------|--------|---------|--------|-------|
       6|kawhi   |leo      |canada  |toronto|
       1|trk     |ttl      |Hlavna 5|TNO    |
       2|doe     |jon      |CA      |GS     |
       3|ewong   |samatha  |SFR     |Dallas |
       5|petofi  |alex     |var     |BP     |
       4|bbking  |bbe      |hemp    |ams    |
```

```sql
SELECT * FROM trk_test_02 ORDER BY dep, city;

systemid|dep       |city|
--------|----------|----|
       2|DEVOPS    |BP  |
       7|DEVOPS    |NYC |
       3|HR        |SF  |
       1|ITOPS     |BA  |
       5|ITOPS     |BP  |
       6|ITOPS     |LN  |
       4|MANAGEMENT|LA  |
```

```sql
SELECT * FROM trk_test_02 ORDER BY dep ASC, city DESC;

systemid|dep       |city|
--------|----------|----|
       7|DEVOPS    |NYC |
       2|DEVOPS    |BP  |
       3|HR        |SF  |
       6|ITOPS     |LN  |
       5|ITOPS     |BP  |
       1|ITOPS     |BA  |
       4|MANAGEMENT|LA  |
```

<a href='#^'>^^^</a>

---

<h3 id='limit'>limit</h3>

```sql
SELECT * FROM Customers LIMIT 3;

personid|lastname|firstname|address |city  |
--------|--------|---------|--------|------|
       1|trk     |ttl      |Hlavna 5|TNO   |
       2|doe     |jon      |CA      |GS    |
       3|ewong   |samatha  |SFR     |Dallas|
```

<a href='#^'>^^^</a>

---

<h3 id='minmax'>min, max</h3>

```sql
SELECT MIN(systemid) AS SmallestSysid FROM trk_test_02;

smallestsysid|
-------------|
            1|
```

```sql
SELECT MAX(systemid) AS LargestSysid FROM trk_test_02;

largestsysid|
------------|
           7|
```

<a href='#^'>^^^</a>

---

<h3 id='countavgsum'>count, avg, sum</h3>

```sql
SELECT COUNT(personid) FROM trk_test_01;

count|
-----|
    6|
```

```sql
SELECT COUNT(DISTINCT city) FROM trk_test_02;

count|
-----|
    6|
```

```sql
SELECT AVG(personid) FROM trk_test_01;

avg               |
------------------|
3.5000000000000000|
```

```sql
SELECT SUM(personid) FROM trk_test_01;

sum|
---|
 21|
```

<a href='#^'>^^^</a>

---

<h3 id='between'>between</h3>

```sql
SELECT * FROM trk_test_01 WHERE personid BETWEEN 2 AND 4;

personid|lastname|firstname|address|city  |
--------|--------|---------|-------|------|
       2|doe     |jon      |CA     |GS    |
       3|ewong   |samatha  |SFR    |Dallas|
       4|bbking  |bbe      |hemp   |ams   |
```

```sql
SELECT * FROM trk_test_01 WHERE personid not BETWEEN 2 AND 4;

personid|lastname|firstname|address |city   |
--------|--------|---------|--------|-------|
       1|trk     |ttl      |Hlavna 5|TNO    |
       6|kawhi   |leo      |canada  |toronto|
       5|petofi  |alex     |var     |BP     |
```

```sql
SELECT * FROM trk_test_01 WHERE personid BETWEEN 2 AND 4 AND NOT lastname IN ('doe');

personid|lastname|firstname|address|city  |
--------|--------|---------|-------|------|
       3|ewong   |samatha  |SFR    |Dallas|
       4|bbking  |bbe      |hemp   |ams   |
```

```sql
SELECT * FROM trk_test_01 WHERE city BETWEEN 'GS' AND 'ams' ORDER BY city;
```

<a href='#^'>^^^</a>

---

<h3 id='in'>in</h3>

```sql
SELECT address FROM trk_test_01 WHERE city IN ('GS', 'Dallas', 'toronto');

address|
-------|
CA     |
SFR    |
canada |
```

```sql
SELECT address FROM trk_test_01 WHERE city NOT IN ('GS', 'Dallas', 'toronto');

address |
--------|
Hlavna 5|
hemp    |
var     |
```

```sql
SELECT * FROM trk_test_01 WHERE city IN (SELECT city FROM trk_test_02); -- compare two columns from two different tables

personid|lastname|firstname|address|city|
--------|--------|---------|-------|----|
       5|petofi  |alex     |var    |BP  |
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

<h3 id='alias'>ALIAS</h3>

```sql
SELECT personid AS PI, firstname AS FI FROM trk_test_01;
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

<h3 id='join'>JOIN</h3>

```sql
SELECT trk_test_01.personid, trk_test_01.lastname, trk_test_02.dep 
FROM trk_test_01 INNER JOIN trk_test_02 ON trk_test_01.personid=trk_test_02.systemid;
```

<a href='#^'>^^^</a>

---

<h3 id='union'>UNION</h3>

```sql
SELECT city FROM trk_test_01 UNION SELECT city FROM trk_test_02 ORDER BY city --without duplicates
SELECT city FROM trk_test_01 UNION ALL SELECT city FROM trk_test_02 ORDER BY city --with duplicates
```

<a href='#^'>^^^</a>

---

<h3 id=''></h3>

<a href='#^'>^^^</a>

---
