
SELECT DISTINCT
======

[]()

---

The SELECT DISTINCT statement is used to return only distinct (different) values.

---

```SQL
SELECT DISTINCT column1, column2, ...
FROM table_name;
```

```SQL
SELECT DISTINCT Country FROM Customers;
```

```SQL
--The following SQL statement lists the number of different (distinct) customer countries:
SELECT COUNT(DISTINCT Country) FROM Customers;
```

```SQL
SELECT Count(*) AS DistinctCountries
FROM (SELECT DISTINCT Country FROM Customers);
```
