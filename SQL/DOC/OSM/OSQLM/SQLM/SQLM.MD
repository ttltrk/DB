
---

###### [改善](https://github.com/ttltrk/0C/blob/master/README.MD) - [.co.](https://github.com/ttltrk/PRG/blob/master/CODING.MD) - [manuals](https://github.com/ttltrk/PRG/blob/master/MAN.MD) - [most used manuals](https://github.com/ttltrk/PRG/blob/master/MUM.MD)

###### [改善](https://github.com/ttltrk/0C/blob/master/README.MD) - [.co.](https://github.com/ttltrk/PRG/blob/master/CODING.MD) - [manuals](https://github.com/ttltrk/PRG/blob/master/MAN.MD) - [basic manuals](https://github.com/ttltrk/PRG/blob/master/MANUALS.MD) - [database](https://github.com/ttltrk/DB/blob/master/DBM/DBM.MD) - [SQL](https://github.com/ttltrk/DB/blob/master/SQL/DOC/OSM/OSM.MD) - [own manuals](https://github.com/ttltrk/DB/blob/master/SQL/DOC/OSM/OSQLM/OSQLM.MD)

###### [PY](https://github.com/ttltrk/PRG/blob/master/PY/DOC/PYF/PYF.MD) - [SS](https://github.com/ttltrk/ELSE/blob/master/SHELL/OSSM/SSCR/SSCR.MD)

---

<h3 id='^'>SQL</h3>

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
SELECT * FROM Customers;
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

<h3 id=''></h3>

<a href='#^'>^^^</a>

---

<h3 id=''></h3>

<a href='#^'>^^^</a>

---
