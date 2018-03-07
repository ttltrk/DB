
WHERE
======

[]()

---

The WHERE clause is used to filter records.

---

```SQL
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```

---

```SQL
SELECT * FROM Customers
WHERE Country='Mexico';
```

```SQL
SELECT * FROM Customers
WHERE CustomerID=1;
```

---

OPERATORS IN THE WHERE CLAUSE

|Operator|Description|
|--------|-----------|
|=|	Equal|
|<>|	Not equal. Note: In some versions of SQL this operator may be written as !=|
|>|	Greater than|
|<|	Less than|
|>=|	Greater than or equal|
|<=|	Less than or equal|
|BETWEEN|	Between an inclusive range|
|LIKE|	Search for a pattern|
|IN|	To specify multiple possible values for a column|

---
