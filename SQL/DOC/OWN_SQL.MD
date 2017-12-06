
Basic Queries
======

```SQL
SELECT * FROM emp WHERE job = 'MANAGER';
SELECT * FROM emp WHERE job != 'MANAGER';
```

```SQL
SELECT * FROM emp WHERE job = 'SALESMAN' AND sal = 1500;
SELECT * FROM emp WHERE job = 'SALESMAN' AND sal < 2500;
SELECT * FROM emp WHERE job = 'SALESMAN' AND sal <= 3000;
SELECT * FROM emp WHERE job = 'CLERK' OR job = 'SALESMAN';
```

```SQL
SELECT ename, hiredate, deptno FROM emp WHERE deptno IN (20, 30);
SELECT ename, hiredate FROM emp WHERE ename IN ('FORD', 'SMITH');
SELECT ename, hiredate FROM emp WHERE ename NOT IN ('FORD', 'SMITH');
```

```SQL
SELECT * FROM emp WHERE hiredate BETWEEN '05/01/1981' AND '01/12/1983';
SELECT * FROM emp WHERE sal NOT BETWEEN 1000 AND 2000;
```

```SQL
SELECT * FROM emp WHERE comm IS NULL;
SELECT * FROM emp WHERE comm IS NOT NULL;
```
