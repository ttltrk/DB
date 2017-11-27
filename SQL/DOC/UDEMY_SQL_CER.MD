
[The Complete Oracle SQL Certification Course](https://www.udemy.com/the-complete-oracle-sql-certification-course/learn/v4/content)
======
 
### Section 1 - Database Basics
  * <a href='#1'>1 - Oracle Database Introduction & Basics of Tables</a>
  * <a href='#2'>2 - Setting Up the SQL Development Environment</a>
  
### Section 2 - Single Table Queries
  * <a href='#3'>3 - Retrieving Data Using the SELECT Clause</a>
  * <a href='#4'>4 - Using the WHERE Clause</a>
  * <a href='#5'>5 - Using Operators in the WHERE Clause</a>
  * <a href='#6'>6 - Combining WHERE, AND & OR with Operators</a>
  * <a href='#7'>7 - Query Filtering Continued BETWEEN, IN and NULL</a>
  * <a href='#8'>8 - Query Filtering Conditions & Operator Precedence</a>
  * <a href='#9'>9 - Ordering, Concatenating and Aliasing Query Results</a>

### Section 3 - Single Row Functions
  * <a href='#10'>10 - Single Row Functions (SRF) & Using the Dual Table</a>
  * <a href='#11'>11 - Using Functions in WHERE and Character Based SRFs</a>
  * <a href='#12'>12 - Numeric and Date Data type SRFs</a>
  * <a href='#13'>13 - Conversion SRFs & Date Formatting</a>
  * <a href='#14'>14 - Concluding SRFs & NULL / NULLIF Functions</a>
  
### Section 4 - Grouping Functions (Exercises and Solutions In the Lectures)
  * <a href='#15'>15 - Grouping Functions MIN, MAX, AVG, COUNT</a>
  * <a href='#16'>16 - GROUP BY Clause HAVING Clause</a>
  * <a href='#17'>17 - More Practice With The GROUP BY Clause</a>

### Section 5 - Mult-Table Queries and Joins (Exercises and Solutions in the Lectures)
  * <a href='#18'>18 - SELECT within SELECT (Subqueries)</a>
  * <a href='#19'>19 - Relating Tables Together Using JOINs</a>
  * <a href='#20'>20 - Joins Continued INNER & OUTER Joins</a>
  * <a href='#21'>21 - More Joins With Correlated Subqueries</a>

### Section 6 - Creating, ALtering and Updating Tables Using SQL
  * <a href='#22'>22 - Creating your own tables and Design Considerations</a>
  * <a href='#23'>23 - Inserting Data into our Table</a>
  * <a href='#24'>24 - Create Table With a Primary Key Constraint</a>
  * <a href='#25'>25 - Using ALTER to modify the tavle structure</a>
  * <a href='#26'>26 - Create Table with SELECT + UPDATE Data</a>
  * <a href='#27'>27 - DELETE, TRUNCATE, and DROP Commands</a>
  * <a href='#28'>28 - Working With Database Indexes (Newly Added)</a>
  * <a href='#29'>29 - System Tables, Pseudo Columns & Deleting Duplicates (Newly Added)</a>
  * <a href='#30'>30 - Views and Other Objects and Commands (Newly Added)</a>
  
Database Basics
------

### <h3 id='1'>1 - Oracle Database Introduction & Basics of Tables</h3>

[[Oracle Database Introduction & Basics of Tables.udemy](https://www.udemy.com/the-complete-oracle-sql-certification-course/learn/v4/t/lecture/5484492?start=0)]

### <h3 id='2'>2 - Setting Up the SQL Development Environment</h3>

[[Setting Up the SQL Development Environment.udemy](https://www.udemy.com/the-complete-oracle-sql-certification-course/learn/v4/t/lecture/5484522?start=0)]

Single Table Queries
------

### <h3 id='3'>3 - Retrieving Data Using the SELECT Clause</h3>

[[Retrieving Data Using the SELECT Clause.udemy](https://www.udemy.com/the-complete-oracle-sql-certification-course/learn/v4/t/lecture/5484526?start=0)]

### <h3 id='4'>4 - Using the WHERE Clause</h3>

[[Using the WHERE Clause.udemy](https://www.udemy.com/the-complete-oracle-sql-certification-course/learn/v4/t/lecture/5484530?start=0)]

### <h3 id='5'>5 - Using Operators in the WHERE Clause</h3>

[[Using Operators in the WHERE Clause.udemy](https://www.udemy.com/the-complete-oracle-sql-certification-course/learn/v4/t/lecture/5484532?start=0)]

WHERE

```SQL
--List Out, all the managers from EMP
SELECT * FROM EMP
WHERE JOB = 'MANAGER';

>>>
EMPNO	ENAME	JOB	MGR	HIREDATE	SAL	COMM	DEPTNO
7698	BLAKE	MANAGER	7839	05/01/1981	2850	-	30
7782	CLARK	MANAGER	7839	06/09/1981	2450	-	10
7566	JONES	MANAGER	7839	04/02/1981	2975	-	20
>>>
```

```SQL
--List Out, all the jobs without MANAGER from EMP
SELECT * FROM EMP
WHERE JOB != 'MANAGER';

>>>
EMPNO	ENAME	JOB	MGR	HIREDATE	SAL	COMM	DEPTNO
7839	KING	PRESIDENT	-	11/17/1981	5000	-	10
7788	SCOTT	ANALYST	7566	12/09/1982	3000	-	20
7902	FORD	ANALYST	7566	12/03/1981	3000	-	20
7369	SMITH	CLERK	7902	12/17/1980	800	-	20
7499	ALLEN	SALESMAN	7698	02/20/1981	1600	300	30
7521	WARD	SALESMAN	7698	02/22/1981	1250	500	30
...
>>>
```

```SQL
--List Out, all the salesman with salary 1500 from EMP
SELECT * FROM EMP
WHERE JOB = 'SALESMAN'
AND SAL = 1500;

>>>
EMPNO	ENAME	JOB	MGR	HIREDATE	SAL	COMM	DEPTNO
7844	TURNER	SALESMAN	7698	09/08/1981	1500	0	30
>>>
```

```SQL
--List Out, all the salesman with salary less than 2500 from EMP
SELECT * FROM EMP
WHERE JOB = 'SALESMAN'
AND SAL < 2500;

>>>
EMPNO	ENAME	JOB	MGR	HIREDATE	SAL	COMM	DEPTNO
7499	ALLEN	SALESMAN	7698	02/20/1981	1600	300	30
7521	WARD	SALESMAN	7698	02/22/1981	1250	500	30
7654	MARTIN	SALESMAN	7698	09/28/1981	1250	1400	30
7844	TURNER	SALESMAN	7698	09/08/1981	1500	0	30
>>>
```

```SQL
--List Out, all the salesman with salary less than or equal to 3000 from EMP
SELECT * FROM EMP
WHERE JOB = 'SALESMAN'
AND SAL <= 3000;

>>>
EMPNO	ENAME	JOB	MGR	HIREDATE	SAL	COMM	DEPTNO
7499	ALLEN	SALESMAN	7698	02/20/1981	1600	300	30
7521	WARD	SALESMAN	7698	02/22/1981	1250	500	30
7654	MARTIN	SALESMAN	7698	09/28/1981	1250	1400	30
7844	TURNER	SALESMAN	7698	09/08/1981	1500	0	30
>>>
```

```SQL
--Return the employees who have a comission greater than their salary
SELECT * FROM EMP
WHERE SAL < COMM;

>>>
EMPNO	ENAME	JOB	MGR	HIREDATE	SAL	COMM	DEPTNO
7654	MARTIN	SALESMAN	7698	09/28/1981	1250	1400	30
>>>
```

```SQL
--Get all employees that are not managers and have sal greater than 2500 and also work in dep no#20
SELECT * FROM EMP
WHERE JOB != 'MANAGERS' 
AND SAL > 2500
AND DEPTNO = 20;

>>>
EMPNO	ENAME	JOB	MGR	HIREDATE	SAL	COMM	DEPTNO
7566	JONES	MANAGER	7839	04/02/1981	2975	-	20
7788	SCOTT	ANALYST	7566	12/09/1982	3000	-	20
7902	FORD	ANALYST	7566	12/03/1981	3000	-	20
>>>
```

### <h3 id='6'>6 - Combining WHERE, AND & OR with Operators</h3>

[[Combining WHERE, AND & OR with Operators.udemy](https://www.udemy.com/the-complete-oracle-sql-certification-course/learn/v4/t/lecture/5484538?start=0)]

OR

```SQL
--Get all employees that are clerks and salesmans.
SELECT * FROM EMP
WHERE JOB='CLERK'
OR JOB='SALESMAN';

>>>
EMPNO	ENAME	JOB	MGR	HIREDATE	SAL	COMM	DEPTNO
7369	SMITH	CLERK	7902	12/17/1980	800	-	20
7499	ALLEN	SALESMAN	7698	02/20/1981	1600	300	30
7521	WARD	SALESMAN	7698	02/22/1981	1250	500	30
7654	MARTIN	SALESMAN	7698	09/28/1981	1250	1400	30
...
>>>
```

AND

```SQL
--Get the names of those employees that are not managers nor salesman and have a salary greater than or
--equal to 2000
SELECT * FROM EMP
WHERE JOB != 'MANAGER'
AND JOB !='SALESMAN'
AND SAL >= 2000;

>>>
EMPNO	ENAME	JOB	MGR	HIREDATE	SAL	COMM	DEPTNO
7839	KING	PRESIDENT	-	11/17/1981	5000	-	10
7788	SCOTT	ANALYST	7566	12/09/1982	3000	-	20
7902	FORD	ANALYST	7566	12/03/1981	3000	-	20
>>>
```
### <h3 id='7'>7 - Query Filtering Continued BETWEEN, IN and NULL</h3>

[[Query Filtering Continued BETWEEN, IN and NULL.udemy](https://www.udemy.com/the-complete-oracle-sql-certification-course/learn/v4/t/lecture/5484542?start=0)]

IN

```SQL
--Get the names of the employees that works in Dallas and in Chicago
SELECT ename, hiredate, deptno FROM EMP
WHERE DEPTNO IN (20, 30);

>>>
ENAME	HIREDATE	DEPTNO
BLAKE	05/01/1981	30
JONES	04/02/1981	20
SCOTT	12/09/1982	20
FORD	12/03/1981	20
SMITH	12/17/1980	20
...
>>>
```

```SQL
--get the mentioned names
SELECT ename, hiredate
FROM EMP
WHERE ENAME IN ('FORD', 'SMITH');

>>>
ENAME	HIREDATE
FORD	12/03/1981
SMITH	12/17/1980
>>>
```

NOT IN

```SQL
get all the names without the selected ones
SELECT ename, hiredate
FROM EMP
WHERE ENAME NOT IN ('FORD', 'SMITH');

>>>
ENAME	HIREDATE
KING	11/17/1981
BLAKE	05/01/1981
CLARK	06/09/1981
JONES	04/02/1981
SCOTT	12/09/1982
...
>>>
```

BETWEEN

```SQL
--between the selected range
SELECT * FROM EMP
WHERE hiredate 
BETWEEN '05/01/1981' AND '01/12/1983';

>>>
EMPNO	ENAME	JOB	MGR	HIREDATE	SAL	COMM	DEPTNO
7839	KING	PRESIDENT	-	11/17/1981	5000	-	10
7698	BLAKE	MANAGER	7839	05/01/1981	2850	-	30
7782	CLARK	MANAGER	7839	06/09/1981	2450	-	10
7788	SCOTT	ANALYST	7566	12/09/1982	3000	-	20
7902	FORD	ANALYST	7566	12/03/1981	3000	-	20
7654	MARTIN	SALESMAN	7698	09/28/1981	1250	1400	30
...
>>>
```

NOT BETWEEN

```SQL
SELECT * FROM EMP
WHERE SAL 
NOT BETWEEN 1000 AND 2000;

>>>
EMPNO	ENAME	JOB	MGR	HIREDATE	SAL	COMM	DEPTNO
7839	KING	PRESIDENT	-	11/17/1981	5000	-	10
7698	BLAKE	MANAGER	7839	05/01/1981	2850	-	30
7782	CLARK	MANAGER	7839	06/09/1981	2450	-	10
7566	JONES	MANAGER	7839	04/02/1981	2975	-	20
7788	SCOTT	ANALYST	7566	12/09/1982	3000	-	20
...
>>>
```

NULL

```SQL
--records with no data
SELECT * FROM EMP
WHERE COMM IS NULL;

>>>
EMPNO	ENAME	JOB	MGR	HIREDATE	SAL	COMM	DEPTNO
7839	KING	PRESIDENT	-	11/17/1981	5000	-	10
7698	BLAKE	MANAGER	7839	05/01/1981	2850	-	30
7782	CLARK	MANAGER	7839	06/09/1981	2450	-	10
7566	JONES	MANAGER	7839	04/02/1981	2975	-	20
...
>>>
```

NOT NULL

```SQL
SELECT * FROM EMP
WHERE COMM IS NOT NULL;

>>>
EMPNO	ENAME	JOB	MGR	HIREDATE	SAL	COMM	DEPTNO
7499	ALLEN	SALESMAN	7698	02/20/1981	1600	300	30
7521	WARD	SALESMAN	7698	02/22/1981	1250	500	30
7654	MARTIN	SALESMAN	7698	09/28/1981	1250	1400	30
...
>>>
```

### <h3 id='8'>8 - Query Filtering Conditions & Operator Precedence</h3>

[[Query Filtering Conditions & Operator Precedence.udemy](https://www.udemy.com/the-complete-oracle-sql-certification-course/learn/v4/t/lecture/5484550?start=0)]

```SQL
-- all employees with null and 0 in COMM and SAL is in the range 1100-5000 and not equal to 1500
SELECT * FROM EMP
WHERE (COMM IS NULL OR COMM = 0)
AND SAL > 1100 
AND SAL < 5000
AND SAL <> 1500;

>>>
EMPNO	ENAME	JOB	MGR	HIREDATE	SAL	COMM	DEPTNO
7698	BLAKE	MANAGER	7839	05/01/1981	2850	-	30
7782	CLARK	MANAGER	7839	06/09/1981	2450	-	10
7566	JONES	MANAGER	7839	04/02/1981	2975	-	20
...
>>>
```

```SQL
-- all salesman with comm 300 and more than 1000
SELECT * FROM EMP
WHERE JOB = 'SALESMAN'
AND (COMM = 300 OR COMM > 1000);

>>>
EMPNO	ENAME	JOB	MGR	HIREDATE	SAL	COMM	DEPTNO
7499	ALLEN	SALESMAN	7698	02/20/1981	1600	300	30
7654	MARTIN	SALESMAN	7698	09/28/1981	1250	1400	30
>>>
```
### <h3 id='9'>9 - Ordering, Concatenating and Aliasing Query Results</h3>

[[Ordering, Concatenating and Aliasing Query Results.udemy](https://www.udemy.com/the-complete-oracle-sql-certification-course/learn/v4/t/lecture/5484552?start=0)]

```SQL
--return back the ENAME as EMPLOYEE NAME, SAL as SALARY and COMM as COMMISION
SELECT ENAME "EMPLOYEE NAME", SAL SALARY, COMM COMMISION
FROM EMP;

>>>
EMPLOYEE NAME	SALARY	COMMISION
KING	5000	-
BLAKE	2850	-
CLARK	2450	-
JONES	2975	-
...
>>>
```

```SQL
--concatenating strings
SELECT 'hello my name is ' || ENAME
FROM EMP;

>>>
hello my name is KING
hello my name is BLAKE
hello my name is CLARK
hello my name is JONES
...
>>>
```

```SQL
--concatenating strings and rename the ENAME to concatenated value
SELECT 'hello my name is ' || ENAME AS "concatenated value"
FROM EMP;

>>>
hello my name is KING
hello my name is BLAKE
hello my name is CLARK
hello my name is JONES
...
>>>
```

```SQL
--concatenating strings and rename ENAME to employee makes per month
SELECT ENAME || ' makes $' || SAL ||  ' per month' AS "employee makes per month"
FROM EMP;

>>>
KING makes $5000 per month
BLAKE makes $2850 per month
CLARK makes $2450 per month
...
>>>
```

```SQL
SELECT ENAME, SAL
FROM EMP
ORDER BY ENAME ASC;

>>>
ENAME	SAL
ADAMS	1100
ALLEN	1600
BLAKE	2850
CLARK	2450
...
>>>
```

```SQL
SELECT ENAME, SAL
FROM EMP
ORDER BY ENAME DESC;

>>>
ENAME	SAL
WARD	1250
TURNER	1500
SMITH	800
SCOTT	3000
...
>>>
```

```SQL
SELECT DEPTNO, SAL, ENAME
FROM EMP
ORDER BY DEPTNO, SAL;

>>>
DEPTNO	SAL	ENAME
10	1300	MILLER
10	2450	CLARK
10	5000	KING
20	800	SMITH
20	1100	ADAMS
20	2975	JONE
...
>>>
```

Single Row Functions
------

### <h3 id='10'>10 - Single Row Functions (SRF) & Using the Dual Table</h3>

[[Single Row Functions (SRF) & Using the Dual Table.udemy](https://www.udemy.com/the-complete-oracle-sql-certification-course/learn/v4/t/lecture/5484554?start=0)]

```SQL
SELECT 'my name is ' || ename as sentence
FROM emp;

>>>
SENTENCE
my name is KING
my name is BLAKE
my name is CLARK
my name is JONES
...
>>>
```

CONCAT

```SQL
SELECT CONCAT('my name is ', ename) as sentence
FROM emp;

>>>
SENTENCE
my name is KING
my name is BLAKE
my name is CLARK
my name is JONES
...
>>>
```

```SQL
SELECT * FROM DUAL;

>>>
DUMMY
X
>>>
```

```SQL
SELECT 'pizza' AS FOOD, 'fanta' AS DRINK FROM DUAL;

>>>
FOOD	DRINK
pizza	fanta
>>>
```

```SQL
SELECT 'pizza' AS FOOD, 'fanta' AS DRINK, CONCAT ('hello', ' john') AS NAME
FROM DUAL;

>>>
FOOD	DRINK	NAME
pizza	fanta	hello john
>>>
```

LOWER

```SQL
SELECT lower(ename) AS name
FROM emp;

>>>
NAME
king
blake
clark
jones
...
>>>
```

```SQL
SELECT CONCAT(lower(ename), ' is the name') AS name
FROM emp;

>>>
NAME
king is the name
blake is the name
clark is the name
jones is the name
...
>>>
```

```SQL
SELECT CONCAT(lower(ename), upper(' is the name')) AS name
FROM emp;

>>>
NAME
king IS THE NAME
blake IS THE NAME
clark IS THE NAME
jones IS THE NAME
...
>>>
```

```SQL
SELECT CONCAT (CONCAT (lower(ename), upper(' is the name ') ), CONCAT ('and their job is: ', job ) ) AS MAIN
FROM emp
WHERE deptno = 20;

>>>
MAIN
jones IS THE NAME and their job is: MANAGER
scott IS THE NAME and their job is: ANALYST
ford IS THE NAME and their job is: ANALYST
smith IS THE NAME and their job is: CLERK
adams IS THE NAME and their job is: CLERK
>>>
```

### <h3 id='11'>11 - Using Functions in WHERE and Character Based SRFs</h3>

[[Using Functions in WHERE and Character Based SRFs.udemy](https://www.udemy.com/the-complete-oracle-sql-certification-course/learn/v4/t/lecture/5484556?start=0)]

LOWER

```SQL
SELECT JOB FROM emp
WHERE job = lower('MANAGER');

>>>
np data found
>>>
```

UPPER

```SQL
SELECT JOB FROM emp
WHERE job = upper('MANAGER');

>>>
JOB
MANAGER
MANAGER
MANAGER
>>>
```

INITCAP

```SQL
SELECT INITCAP ('hello world') as hello
FROM DUAL;

>>>
HELLO
Hello World
>>>
```

LENGTH

```SQL
SELECT LENGTH ('hello world') as hello
FROM DUAL;

>>>
11
>>>
```

```SQL
SELECT LENGTH (ename) as length
FROM emp;

>>>
LENGTH
4
5
5
5
5
4
5
5
...
>>>
```

```SQL
SELECT ename, LENGTH (ename) as length
FROM emp;

>>>
ENAME	LENGTH
KING	4
BLAKE	5
CLARK	5
JONES	5
...
>>>
```

```SQL
SELECT ename, LENGTH (ename) as length
FROM emp
WHERE LENGTH (ename) = 6;

>>>
ENAME	LENGTH
MARTIN	6
TURNER	6
MILLER	6
>>>
```

SUBSTR

```SQL
SELECT 'hello', SUBSTR ('hello', 2, 2) as substring
FROM DUAL;

>>>
'HELLO'	SUBSTRING
hello	el
>>>
```

```SQL
SELECT 'hello', SUBSTR ('hello', 2) as substring
FROM DUAL;

>>>
'HELLO'	SUBSTRING
hello	ello
>>>
```

LPAD

```SQL
SELECT LPAD ('hello', 10, '&') as LPAD
FROM DUAL;

>>>
LPAD
&&&&&hello
>>>
```

RPAD

```SQL
SELECT RPAD ('hello', 10, '&') as RPAD
FROM DUAL;

>>>
RPAD
hello&&&&&
>>>
```

LTRIM

```SQL
SELECT LTRIM ('hello','h') as LTRIM
FROM DUAL;

>>>
LTRIM
ello
>>>
```

RTRIM

```SQL
SELECT RTRIM ('hello','o') as RTRIM
FROM DUAL;

>>>
RTRIM
hell
>>>
```

### <h3 id='12'>12 - Numeric and Date Data type SRFs</h3>

[[Numeric and Date Data type SRFs.udemy](https://www.udemy.com/the-complete-oracle-sql-certification-course/learn/v4/t/lecture/5484564?start=0)]

ROUND

```SQL
SELECT ROUND (107.088, 2) AS R
FROM DUAL;

>>>
R
107.09
>>>
```

TRUNC

```SQL
SELECT TRUNC (107.0888476563839) AS T
FROM DUAL;

>>>
T
107
>>>
```

```SQL
SELECT TRUNC (107.0888476563839, 3) AS T
FROM DUAL;

>>>
T
107.088
>>>
```

```SQL
SELECT TRUNC (SYSTIMESTAMP) AS TRNC
FROM DUAL;

>>>
TRNC
11/06/2017
>>>
```

```SQL
SELECT ename, hiredate , TRUNC(hiredate, 'MONTH') AS TRNC
FROM emp
WHERE TRUNC(hiredate, 'YEAR') = '01/01/1982';

>>>
ENAME	HIREDATE	TRNC
SCOTT	12/09/1982	12/01/1982
MILLER	01/23/1982	01/01/1982
>>>
```

SYSDATE

```SQL
SELECT SYSDATE
FROM DUAL;

>>>
SYSDATE
11/06/2017
>>>
```

SYSTIMESTAMP

```SQL
SELECT SYSTIMESTAMP
FROM DUAL;

>>>
SYSTIMESTAMP
06-NOV-17 05.02.55.570610 AM +00:00
>>>
```

ADD_MONTHS

```SQL
SELECT ADD_MONTHS('11/4/2017', 3) AS ADDM
FROM DUAL;

>>>
ADDM
02/04/2018
>>>
```

```SQL
SELECT ADD_MONTHS('11/4/2017', -3) AS ADDM
FROM DUAL;

>>>
ADDM
08/04/2017
>>>
```

```SQL
SELECT ADD_MONTHS(SYSDATE, 3) AS ADDM
FROM DUAL;

>>>
ADDM
02/06/2018
>>>
```

MONTHS_BETWEEN

```SQL
SELECT MONTHS_BETWEEN('12/10/2017', '12/10/2015') AS MBW
FROM DUAL;

>>>
MBW
24
>>>
```

### <h3 id='13'>13 - Conversion SRFs & Date Formatting</h3>

[[Conversion SRFs & Date Formatting.udemy](https://www.udemy.com/the-complete-oracle-sql-certification-course/learn/v4/t/lecture/5484568?start=0)]

TO_CHAR

```SQL
SELECT TO_CHAR(sysdate, 'mm-dd-yy') AS ACTDATE
FROM DUAL;

>>>
ACTDATE
11-07-17
>>>
```

```SQL
SELECT TO_CHAR(sysdate, 'mm/dd/yy') AS ACTDATE
FROM DUAL;

>>>
ACTDATE
11/07/17
>>>
```

```SQL
SELECT TO_CHAR(sysdate, 'yyyy-mon-dd') AS ACTDATE
FROM DUAL;

>>>
ACTDATE
2017-nov-07
>>>
```

```SQL
SELECT ename, sal, TO_CHAR(sal, '$99,999.99') AS SAL_UPD
FROM emp;

>>>
ENAME	SAL	SAL_UPD
KING	5000	$5,000.00
BLAKE	2850	$2,850.00
CLARK	2450	$2,450.00
JONES	2975	$2,975.00
SCOTT	3000	$3,000.00
...
>>>
```

```SQL
SELECT TO_DATE('2017-10-12', 'yyyy-mm-dd') as REQDATE
FROM dual;

>>>
REQDATE
10/12/2017
>>>
```

```SQL
SELECT ADD_MONTHS(TO_DATE('2017-10-12', 'yyyy-mm-dd'), 2) as REQDATE
FROM dual;

>>>
REQDATE
12/12/2017
>>>
```

### <h3 id='14'>14 - Concluding SRFs & NULL / NULLIF Functions</h3>

[[Concluding SRFs & NULL / NULLIF Functions.udemy](https://www.udemy.com/the-complete-oracle-sql-certification-course/learn/v4/t/lecture/5484574?start=0)]

```SQL
SELECT ename, job, sal, comm
FROM emp
WHERE empno IN (7839, 7698, 7566, 7654);

>>>
ENAME	JOB	SAL	COMM
JONES	MANAGER	2975	-
MARTIN	SALESMAN	1250	1400
BLAKE	MANAGER	2850	-
KING	PRESIDENT	5000	-
>>>
```

NVL

```SQL
SELECT ename, job, sal, NVL(comm, 0)
FROM emp
WHERE empno IN (7839, 7698, 7566, 7654);

>>>
ENAME	JOB	SAL	NVL(COMM,0)
JONES	MANAGER	2975	0
MARTIN	SALESMAN	1250	1400
BLAKE	MANAGER	2850	0
KING	PRESIDENT	5000	0
>>>
```

```SQL
SELECT ename, job, sal, NVL(to_char(comm), 'No Data Found')
FROM emp
WHERE empno IN (7839, 7698, 7566, 7654);

>>>
ENAME	JOB	SAL	NVL(TO_CHAR(COMM),'NODATAFOUND')
JONES	MANAGER	2975	No Data Found
MARTIN	SALESMAN	1250	1400
BLAKE	MANAGER	2850	No Data Found
KING	PRESIDENT	5000	No Data Found
>>>
```

NULLIF

```SQL
SELECT ename, LENGTH(ename), NULLIF(length(ename), 5)
FROM emp;

>>>
ENAME	LENGTH(ENAME)	NULLIF(LENGTH(ENAME),5)
KING	4	4
BLAKE	5	-
CLARK	5	-
JONES	5	-
SCOTT	5	-
FORD	4	4
SMITH	5	-
ALLEN	5	-
WARD	4	4
MARTIN	6	6
>>>
```

```SQL
SELECT ename, LENGTH(ename), NVL(NULLIF(TO_CHAR(length(ename)), TO_CHAR(5)), 'length is 5') AS UPDATED
FROM emp;

>>>
ENAME	LENGTH(ENAME)	UPDATED
KING	4	4
BLAKE	5	length is 5
CLARK	5	length is 5
JONES	5	length is 5
SCOTT	5	length is 5
FORD	4	4
SMITH	5	length is 5
ALLEN	5	length is 5
WARD	4	4
MARTIN	6	6
>>>
```

Grouping Functions (Exercises and Solutions In the Lectures)
------

### <h3 id='15'>15 - Grouping Functions MIN, MAX, AVG, COUNT</h3>

[[Grouping Functions MIN, MAX, AVG, COUNT.udemy](https://www.udemy.com/the-complete-oracle-sql-certification-course/learn/v4/t/lecture/5484576?start=0)]

MAX

```SQL
SELECT MAX(sal) FROM emp;

>>>
MAX(SAL)
5000
>>>
```

```SQL
SELECT MAX(sal)
FROM emp
WHERE job='MANAGER';

>>>
MAX(SAL)
2975
>>>
```

```SQL
SELECT MAX(sal) FROM emp
WHERE lower(job) LIKE '%manager%';

>>>
MAX(SAL)
2975
>>>
```

MIN

```SQL
SELECT MIN(sal) FROM emp;

>>>
MIN(SAL)
800
>>>
```

SUM

```SQL
SELECT SUM(sal) FROM emp;

>>>
SUM(SAL)
29025
>>>
```

AVG

```SQL
SELECT AVG(sal) FROM emp;

>>>
AVG(SAL)
2073.21
>>>
```

```SQL
SELECT SUM(sal) / count(*) AS COMPUTED_AVG, AVG(sal) AS NATIVE_AVG FROM emp;

>>>
COMPUTED_AVG	NATIVE_AVG
2073.21428571428571428571428571428571429	2073.21428571428571428571428571428571429
>>>
```

COUNT

```SQL
SELECT COUNT(ename) FROM emp;

>>>
COUNT(ENAME)
14
>>>
```

```SQL
SELECT SUM(sal) AS SUM, AVG(sal) AS AVG, MAX(sal) AS MAX, MIN(sal) AS MIN, COUNT(*) FROM emp;

>>>
SUM	AVG	MAX	MIN	COUNT(*)
29025	2073.21428571428571428571428571428571429	5000	800	14
>>>
```

### <h3 id='16'>16 - GROUP BY Clause HAVING Clause</h3>

[[GROUP BY Clause HAVING Clause.udemy](https://www.udemy.com/the-complete-oracle-sql-certification-course/learn/v4/t/lecture/5491338?start=0)]

GROUP BY

```SQL
SELECT AVG(sal) AS salary_average, job
FROM emp
GROUP BY job;

>>>
SALARY_AVERAGE	JOB
1037.5	CLERK
1400	SALESMAN
5000	PRESIDENT
2758.33333333333333333333333333333333333	MANAGER
3000	ANALYST
>>>
```

```SQL
SELECT job
FROM emp
GROUP BY job;

>>>
JOB
CLERK
SALESMAN
PRESIDENT
MANAGER
ANALYST
>>>
```

```SQL
SELECT COUNT(*) AS emp_num_job, job
FROM emp
GROUP BY job;

>>>
EMP_NUM_JOB	JOB
4	CLERK
4	SALESMAN
1	PRESIDENT
3	MANAGER
2	ANALYST
>>>
```

```SQL
SELECT MIN(sal) AS lowest_salary, job
FROM emp
GROUP BY job;

>>>
LOWEST_SALARY	JOB
800	CLERK
1250	SALESMAN
5000	PRESIDENT
2450	MANAGER
3000	ANALYST
>>>
```

```SQL
--same as GROUP BY Func
SELECT DISTINCT job
FROM emp;

>>>
JOB
CLERK
SALESMAN
PRESIDENT
MANAGER
ANALYST
>>>
```

HAVING

```SQL
--will select only the jobs were the emp number is = 2
SELECT COUNT(*) AS EMP_NUM, job
FROM emp
GROUP BY job
HAVING COUNT(*) = 2;

>>>
EMP_NUM	JOB
2	ANALYST
>>>
```

```SQL
SELECT COUNT(*) AS DEP_NUM, deptno
FROM emp
GROUP BY deptno
HAVING COUNT(*) > 3;

>>>
DEP_NUM	DEPTNO
6	30
5	20
>>>
```

```
(1) SELECT
(2) FROM
(3) WHERE
(4) GROUP BY
(5) HAVING
(6) ORDER BY
```

### <h3 id='17'>17 - More Practice With The GROUP BY Clause</h3>

[[More Practice With The GROUP BY Clause.udemy](https://www.udemy.com/the-complete-oracle-sql-certification-course/learn/v4/t/lecture/5491340?start=0)]

GROUP BY

```SQL
SELECT job, count(*) AS emp_num
FROM emp
GROUP BY job;

>>>
JOB	EMP_NUM
CLERK	4
SALESMAN	4
PRESIDENT	1
MANAGER	3
ANALYST	2
>>>
```

```SQL
SELECT deptno, job, count(*) AS empno_diff_dept
FROM emp
GROUP BY deptno, job;

>>>
DEPTNO	JOB	EMPNO_DIFF_DEPT
20	MANAGER	1
20	CLERK	2
30	SALESMAN	4
30	CLERK	1
10	PRESIDENT	1
30	MANAGER	1
10	CLERK	1
10	MANAGER	1
20	ANALYST	2
>>>
```

```SQL
SELECT col_1, col_2, col_3, group_function(aggregate_expression)
FROM tables
[ WHERE conditions ]
GROUP BY col_1, col_2, col_3...col_n
[ ORDER BY conditions ]
```

[[tech on the net](https://www.techonthenet.com/)]

Multi-Table Queries and Joins (Exercieses and Solutions In the Lectures)
------

### <h3 id='18'>18 - SELECT within SELECT (Subqueries)</h3>

[[SELECT within SELECT (Subqueries).udemy](https://www.udemy.com/the-complete-oracle-sql-certification-course/learn/v4/t/lecture/5491342?start=0)]

```SQL
SELECT * FROM dept;

>>>
DEPTNO	DNAME	LOC
10	ACCOUNTING	NEW YORK
20	RESEARCH	DALLAS
30	SALES	CHICAGO
40	OPERATIONS	BOSTON
>>>
```

```SQL
SELECT * FROM dept
WHERE deptno = 30;

>>>
DEPTNO	DNAME	LOC
30	SALES	CHICAGO
>>>
```

```SQL
SELECT * FROM dept
WHERE deptno = (SELECT deptno FROM dept WHERE deptno = 30);

>>>
DEPTNO	DNAME	LOC
30	SALES	CHICAGO
>>>
```

```SQL
SELECT * FROM dept
WHERE deptno < (SELECT deptno FROM dept WHERE deptno = 30);

>>>
DEPTNO	DNAME	LOC
10	ACCOUNTING	NEW YORK
20	RESEARCH	DALLAS
>>>
```

```SQL
SELECT * FROM dept
WHERE deptno < (SELECT deptno FROM dept WHERE deptno = 30)
AND dname = 'ACCOUNTING';

>>>
DEPTNO	DNAME	LOC
10	ACCOUNTING	NEW YORK
>>>
```

```SQL
SELECT * FROM dept;

>>>
DEPTNO	DNAME	LOC
10	ACCOUNTING	NEW YORK
20	RESEARCH	DALLAS
30	SALES	CHICAGO
40	OPERATIONS	BOSTON
>>>
```

```SQL
SELECT * FROM emp
WHERE deptno = (SELECT deptno FROM dept WHERE loc = 'CHICAGO');

>>>
EMPNO	ENAME	JOB	MGR	HIREDATE	SAL	COMM	DEPTNO
7698	BLAKE	MANAGER	7839	05/01/1981	2850	-	30
7499	ALLEN	SALESMAN	7698	02/20/1981	1600	300	30
7521	WARD	SALESMAN	7698	02/22/1981	1250	500	30
7654	MARTIN	SALESMAN	7698	09/28/1981	1250	1400	30
7844	TURNER	SALESMAN	7698	09/08/1981	1500	0	30
7900	JAMES	CLERK	7698	12/03/1981	950	-	30
>>>
```

```SQL
SELECT * FROM emp
WHERE deptno IN (SELECT deptno FROM dept WHERE deptno IN (10, 20));

>>>
EMPNO	ENAME	JOB	MGR	HIREDATE	SAL	COMM	DEPTNO
7839	KING	PRESIDENT	-	11/17/1981	5000	-	10
7782	CLARK	MANAGER	7839	06/09/1981	2450	-	10
7566	JONES	MANAGER	7839	04/02/1981	2975	-	20
7788	SCOTT	ANALYST	7566	12/09/1982	3000	-	20
7902	FORD	ANALYST	7566	12/03/1981	3000	-	20
7369	SMITH	CLERK	7902	12/17/1980	800	-	20
7876	ADAMS	CLERK	7788	01/12/1983	1100	-	20
7934	MILLER	CLERK	7782	01/23/1982	1300	-	10
>>>
```

### <h3 id='19'>19 - Relating Tables Together Using JOINs</h3>

[[Relating Tables Together Using JOINs.udemy](https://www.udemy.com/the-complete-oracle-sql-certification-course/learn/v4/t/lecture/5491344?start=0)]

```SQL
SELECT * FROM emp, dept;

>>>
EMPNO	ENAME	JOB	MGR	HIREDATE	SAL	COMM	DEPTNO	DEPTNO	DNAME	LOC
7839	KING	PRESIDENT	-	11/17/1981	5000	-	10	10	ACCOUNTING	NEW YORK
7698	BLAKE	MANAGER	7839	05/01/1981	2850	-	30	10	ACCOUNTING	NEW YORK
7782	CLARK	MANAGER	7839	06/09/1981	2450	-	10	10	ACCOUNTING	NEW YORK
7566	JONES	MANAGER	7839	04/02/1981	2975	-	20	10	ACCOUNTING	NEW YORK
7788	SCOTT	ANALYST	7566	12/09/1982	3000	-	20	10	ACCOUNTING	NEW YORK
7902	FORD	ANALYST	7566	12/03/1981	3000	-	20	10	ACCOUNTING	NEW YORK
7369	SMITH	CLERK	7902	12/17/1980	800	-	20	10	ACCOUNTING	NEW YORK
7499	ALLEN	SALESMAN	7698	02/20/1981	1600	300	30	10	ACCOUNTING	NEW YORK
7521	WARD	SALESMAN	7698	02/22/1981	1250	500	30	10	ACCOUNTING	NEW YORK
7654	MARTIN	SALESMAN	7698	09/28/1981	1250	1400	30	10	ACCOUNTING	NEW YORK
>>>
```

```SQL
SELECT * FROM emp, dept
WHERE emp.deptno = dept.deptno;

>>>
EMPNO	 ENAME	 JOB	      MGR	  HIREDATE	  SAL	  COMM	DEPTNO	DEPTNO	DNAME	     LOC
7782  	CLARK	 MANAGER	  7839	 06/09/1981	2450	 -	   10	    10	    ACCOUNTING	NEW YORK
7934	  MILLER	CLERK	    7782	 01/23/1982	1300	 -	   10	    10	    ACCOUNTING	NEW YORK
7839	  KING	  PRESIDENT	-	    11/17/1981	5000	 -	   10	    10	    ACCOUNTING	NEW YORK
7902	  FORD	  ANALYST	  7566	 12/03/1981	3000	 -	   20	    20	    RESEARCH	  DALLAS
7788	  SCOTT	 ANALYST	  7566	 12/09/1982	3000	 -	   20	    20	    RESEARCH	  DALLAS
7566	  JONES	 MANAGER	  7839	 04/02/1981	2975	 -	   20	    20	    RESEARCH	  DALLAS
7369	  SMITH	 CLERK	    7902	 12/17/1980	800	  -	   20	    20	    RESEARCH	  DALLAS
7876	  ADAMS	 CLERK	    7788	 01/12/1983	1100	 -	   20	    20	    RESEARCH	  DALLAS
7521	  WARD	  SALESMAN	 7698	 02/22/1981	1250	 500	 30	    30	    SALES	     CHICAGO
7654	  MARTIN	SALESMAN	 7698	 09/28/1981	1250	 1400	30	    30	    SALES	     CHICAGO
>>>
```

```SQL
--employees working in Dallas
SELECT e.ename AS first_name, job, sal, loc, e.deptno
FROM emp e, dept d
WHERE e.deptno = d.deptno
AND loc = 'DALLAS';

>>>
FIRST_NAME	JOB	SAL	LOC	DEPTNO
FORD	ANALYST	3000	DALLAS	20
SCOTT	ANALYST	3000	DALLAS	20
JONES	MANAGER	2975	DALLAS	20
SMITH	CLERK	800	DALLAS	20
ADAMS	CLERK	1100	DALLAS	20

>>>
```

```SQL
SELECT e.ename AS first_name, job, sal, loc, e.deptno
FROM (SELECT * FROM emp WHERE job IN ('MANAGER', 'CLERK')) e, dept d
WHERE e.deptno = d.deptno
AND loc = 'DALLAS';

>>>
FIRST_NAME	JOB	SAL	LOC	DEPTNO
JONES	MANAGER	2975	DALLAS	20
SMITH	CLERK	800	DALLAS	20
ADAMS	CLERK	1100	DALLAS	20
>>>
```

```SQL
SELECT e.ename AS first_name, job, sal, loc, e.deptno
FROM (SELECT * FROM emp WHERE job IN ('MANAGER', 'CLERK')) e, (SELECT * FROM dept WHERE loc = 'DALLAS') d
WHERE e.deptno = d.deptno;

>>>
FIRST_NAME	JOB	SAL	LOC	DEPTNO
JONES	MANAGER	2975	DALLAS	20
SMITH	CLERK	800	DALLAS	20
ADAMS	CLERK	1100	DALLAS	20
>>>
```

### <h3 id='20'>20 - Joins Continued INNER & OUTER Joins</h3>

[[Joins Continued INNER & OUTER Joins.udemy](https://www.udemy.com/the-complete-oracle-sql-certification-course/learn/v4/t/lecture/5491346?start=0)]

INNER JOIN

```SQL
SELECT *
FROM emp, dept
WHERE emp.deptno = dept.deptno;

--iS the same as:
SELECT * 
FROM emp INNER JOIN dept
ON emp.deptno = dept.deptno;

>>>
EMPNO	ENAME	JOB	MGR	HIREDATE	SAL	COMM	DEPTNO	DEPTNO	DNAME	LOC
7782	CLARK	MANAGER	7839	06/09/1981	2450	-	10	10	ACCOUNTING	NEW YORK
7934	MILLER	CLERK	7782	01/23/1982	1300	-	10	10	ACCOUNTING	NEW YORK
7839	KING	PRESIDENT	-	11/17/1981	5000	-	10	10	ACCOUNTING	NEW YORK
7902	FORD	ANALYST	7566	12/03/1981	3000	-	20	20	RESEARCH	DALLAS
7788	SCOTT	ANALYST	7566	12/09/1982	3000	-	20	20	RESEARCH	DALLAS
7566	JONES	MANAGER	7839	04/02/1981	2975	-	20	20	RESEARCH	DALLAS
7369	SMITH	CLERK	7902	12/17/1980	800	-	20	20	RESEARCH	DALLAS
7876	ADAMS	CLERK	7788	01/12/1983	1100	-	20	20	RESEARCH	DALLAS
7521	WARD	SALESMAN	7698	02/22/1981	1250	500	30	30	SALES	CHICAGO
7654	MARTIN	SALESMAN	7698	09/28/1981	1250	1400	30	30	SALES	CHICAGO
>>>
```

RIGHT JOIN

```SQL
--all the records from the right table
SELECT * 
FROM emp RIGHT JOIN dept
ON emp.deptno = dept.deptno;

>>>
EMPNO	ENAME	JOB	MGR	HIREDATE	SAL	COMM	DEPTNO	DEPTNO	DNAME	LOC
7782	CLARK	MANAGER	7839	06/09/1981	2450	-	10	10	ACCOUNTING	NEW YORK
7934	MILLER	CLERK	7782	01/23/1982	1300	-	10	10	ACCOUNTING	NEW YORK
7839	KING	PRESIDENT	-	11/17/1981	5000	-	10	10	ACCOUNTING	NEW YORK
7902	FORD	ANALYST	7566	12/03/1981	3000	-	20	20	RESEARCH	DALLAS
7788	SCOTT	ANALYST	7566	12/09/1982	3000	-	20	20	RESEARCH	DALLAS
7566	JONES	MANAGER	7839	04/02/1981	2975	-	20	20	RESEARCH	DALLAS
7369	SMITH	CLERK	7902	12/17/1980	800	-	20	20	RESEARCH	DALLAS
7876	ADAMS	CLERK	7788	01/12/1983	1100	-	20	20	RESEARCH	DALLAS
7521	WARD	SALESMAN	7698	02/22/1981	1250	500	30	30	SALES	CHICAGO
7654	MARTIN	SALESMAN	7698	09/28/1981	1250	1400	30	30	SALES	CHICAGO
7844	TURNER	SALESMAN	7698	09/08/1981	1500	0	30	30	SALES	CHICAGO
7900	JAMES	CLERK	7698	12/03/1981	950	-	30	30	SALES	CHICAGO
7499	ALLEN	SALESMAN	7698	02/20/1981	1600	300	30	30	SALES	CHICAGO
7698	BLAKE	MANAGER	7839	05/01/1981	2850	-	30	30	SALES	CHICAGO
-	-	-	-	-	-	-	-	40	OPERATIONS	BOSTON
>>>
```

LEFT JOIN

```SQL
--all the records from the left table
SELECT * 
FROM emp LEFT JOIN dept
ON emp.deptno = dept.deptno;

>>>
EMPNO	ENAME	JOB	MGR	HIREDATE	SAL	COMM	DEPTNO	DEPTNO	DNAME	LOC
7839	KING	PRESIDENT	-	11/17/1981	5000	-	10	10	ACCOUNTING	NEW YORK
7698	BLAKE	MANAGER	7839	05/01/1981	2850	-	30	30	SALES	CHICAGO
7782	CLARK	MANAGER	7839	06/09/1981	2450	-	10	10	ACCOUNTING	NEW YORK
7566	JONES	MANAGER	7839	04/02/1981	2975	-	20	20	RESEARCH	DALLAS
7788	SCOTT	ANALYST	7566	12/09/1982	3000	-	20	20	RESEARCH	DALLAS
7902	FORD	ANALYST	7566	12/03/1981	3000	-	20	20	RESEARCH	DALLAS
7369	SMITH	CLERK	7902	12/17/1980	800	-	20	20	RESEARCH	DALLAS
7499	ALLEN	SALESMAN	7698	02/20/1981	1600	300	30	30	SALES	CHICAGO
7521	WARD	SALESMAN	7698	02/22/1981	1250	500	30	30	SALES	CHICAGO
7654	MARTIN	SALESMAN	7698	09/28/1981	1250	1400	30	30	SALES	CHICAGO
7844	TURNER	SALESMAN	7698	09/08/1981	1500	0	30	30	SALES	CHICAGO
7876	ADAMS	CLERK	7788	01/12/1983	1100	-	20	20	RESEARCH	DALLAS
7900	JAMES	CLERK	7698	12/03/1981	950	-	30	30	SALES	CHICAGO
7934	MILLER	CLERK	7782	01/23/1982	1300	-	10	10	ACCOUNTING	NEW YORK
>>>
```

FULL JOIN

```SQL
SELECT * 
FROM emp FULL OUTER JOIN dept
ON emp.deptno = dept.deptno;

>>>
EMPNO	ENAME	JOB	MGR	HIREDATE	SAL	COMM	DEPTNO	DEPTNO	DNAME	LOC
7839	KING	PRESIDENT	-	11/17/1981	5000	-	10	10	ACCOUNTING	NEW YORK
7698	BLAKE	MANAGER	7839	05/01/1981	2850	-	30	30	SALES	CHICAGO
7782	CLARK	MANAGER	7839	06/09/1981	2450	-	10	10	ACCOUNTING	NEW YORK
7566	JONES	MANAGER	7839	04/02/1981	2975	-	20	20	RESEARCH	DALLAS
7788	SCOTT	ANALYST	7566	12/09/1982	3000	-	20	20	RESEARCH	DALLAS
7902	FORD	ANALYST	7566	12/03/1981	3000	-	20	20	RESEARCH	DALLAS
7369	SMITH	CLERK	7902	12/17/1980	800	-	20	20	RESEARCH	DALLAS
7499	ALLEN	SALESMAN	7698	02/20/1981	1600	300	30	30	SALES	CHICAGO
7521	WARD	SALESMAN	7698	02/22/1981	1250	500	30	30	SALES	CHICAGO
7654	MARTIN	SALESMAN	7698	09/28/1981	1250	1400	30	30	SALES	CHICAGO
7844	TURNER	SALESMAN	7698	09/08/1981	1500	0	30	30	SALES	CHICAGO
7876	ADAMS	CLERK	7788	01/12/1983	1100	-	20	20	RESEARCH	DALLAS
7900	JAMES	CLERK	7698	12/03/1981	950	-	30	30	SALES	CHICAGO
7934	MILLER	CLERK	7782	01/23/1982	1300	-	10	10	ACCOUNTING	NEW YORK
-	-	-	-	-	-	-	-	40	OPERATIONS	BOSTON
>>>
```

```SQL
SELECT * 
FROM (SELECT * FROM emp WHERE job = 'SALESMAN') emp FULL OUTER JOIN dept
ON emp.deptno = dept.deptno;

>>>
EMPNO	ENAME	JOB	MGR	HIREDATE	SAL	COMM	DEPTNO	DEPTNO	DNAME	LOC
-	-	-	-	-	-	-	-	10	ACCOUNTING	NEW YORK
-	-	-	-	-	-	-	-	20	RESEARCH	DALLAS
7844	TURNER	SALESMAN	7698	09/08/1981	1500	0	30	30	SALES	CHICAGO
7654	MARTIN	SALESMAN	7698	09/28/1981	1250	1400	30	30	SALES	CHICAGO
7521	WARD	SALESMAN	7698	02/22/1981	1250	500	30	30	SALES	CHICAGO
7499	ALLEN	SALESMAN	7698	02/20/1981	1600	300	30	30	SALES	CHICAGO
-	-	-	-	-	-	-	-	40	OPERATIONS	BOSTON
>>>
```

### <h3 id='21'>21 - More Joins With Correlated Subqueries</h3>

[[More Joins With Correlated Subqueries.udemy](https://www.udemy.com/the-complete-oracle-sql-certification-course/learn/v4/t/lecture/5491348?start=0)]

EXISTS

```SQL
SELECT * FROM emp
WHERE EXISTS (SELECT 'random' FROM dual);

>>>
EMPNO	ENAME	JOB	MGR	HIREDATE	SAL	COMM	DEPTNO
7839	KING	PRESIDENT	-	11/17/1981	5000	-	10
7698	BLAKE	MANAGER	7839	05/01/1981	2850	-	30
7782	CLARK	MANAGER	7839	06/09/1981	2450	-	10
7566	JONES	MANAGER	7839	04/02/1981	2975	-	20
7788	SCOTT	ANALYST	7566	12/09/1982	3000	-	20
7902	FORD	ANALYST	7566	12/03/1981	3000	-	20
7369	SMITH	CLERK	7902	12/17/1980	800	-	20
7499	ALLEN	SALESMAN	7698	02/20/1981	1600	300	30
7521	WARD	SALESMAN	7698	02/22/1981	1250	500	30
7654	MARTIN	SALESMAN	7698	09/28/1981	1250	1400	30
>>>
```

```SQL
SELECT * FROM emp
WHERE EXISTS (SELECT * FROM emp WHERE job = 'PROGRAMMER');

>>>
no data found
>>>
```

CORRELATED SUBQUERY

```SQL
SELECT d.* FROM dept d
WHERE EXISTS (SELECT * FROM emp WHERE d.deptno = emp.deptno);

>>>
DEPTNO	DNAME	LOC
10	ACCOUNTING	NEW YORK
20	RESEARCH	DALLAS
30	SALES	CHICAGO
>>>
```

```SQL
SELECT d.* FROM dept d
WHERE NOT EXISTS (SELECT * FROM emp WHERE d.deptno = emp.deptno)
AND loc = 'BOSTON';

>>>
DEPTNO	DNAME	LOC
40	OPERATIONS	BOSTON
>>>
```

Creating, ALtering and Updating Tables Using SQL
------
  
### <h3 id='22'>22 - Creating your own tables and Design Considerations</h3>

[[Creating your own tables and Design Considerations.udemy](https://www.udemy.com/the-complete-oracle-sql-certification-course/learn/v4/t/lecture/5491350?start=0)]

Primary Key
  * Cannot have duplicates
  * Cannot be Null

```SQL
--EMPNO is the PK
SELECT * FROM emp;

>>>
EMPNO	ENAME	JOB	MGR	HIREDATE	SAL	COMM	DEPTNO
7839	KING	PRESIDENT	-	11/17/1981	5000	-	10
7698	BLAKE	MANAGER	7839	05/01/1981	2850	-	30
7782	CLARK	MANAGER	7839	06/09/1981	2450	-	10
7566	JONES	MANAGER	7839	04/02/1981	2975	-	20
7788	SCOTT	ANALYST	7566	12/09/1982	3000	-	20
7902	FORD	ANALYST	7566	12/03/1981	3000	-	20
7369	SMITH	CLERK	7902	12/17/1980	800	-	20
7499	ALLEN	SALESMAN	7698	02/20/1981	1600	300	30
7521	WARD	SALESMAN	7698	02/22/1981	1250	500	30
7654	MARTIN	SALESMAN	7698	09/28/1981	1250	1400	30
>>>
```

```SQL
--DEPTNO is the PK
SELECT * FROM dept;

>>>
DEPTNO	DNAME	LOC
10	ACCOUNTING	NEW YORK
20	RESEARCH	DALLAS
30	SALES	CHICAGO
40	OPERATIONS	BOSTON
>>>
```

CREATE TABLE

```SQL
CREATE TABLE stores 
(
  store_id number not null,
  city varchar(50)
);

>>>
Table created.

0.03 seconds
>>>
```

#### <h3 id="23">23 - Inserting Data into our Table</h3>

[[Inserting Data into our Table.udemy](https://www.udemy.com/the-complete-oracle-sql-certification-course/learn/v4/t/lecture/5491352?start=0)]

INSERT INTO

```SQL
INSERT INTO stores(store_id, city) VALUES (1, 'San Francisco');
--COMMIT;
SELECT * FROM stores;

>>>
STORE_ID	CITY
1	San Francisco
>>>
```

```SQL
INSERT INTO stores(store_id, city) VALUES (2, 'New York');
--COMMIT;
SELECT * FROM stores;

>>>
STORE_ID	CITY
1	San Francisco
2	New York
>>>
```

INSERT ALL

```SQL
INSERT ALL
  INTO stores(store_id, city) VALUES (4, 'Philadelphia')
  INTO stores(store_id, city) VALUES (5, 'Boston')
  INTO stores(store_id, city) VALUES (6, 'Seattle')
SELECT * FROM DUAL;
SELECT * FROM stores;

>>>
STORE_ID	CITY
1	San Francisco
2	New York
4	Philadelphia
5	Boston
6	Seattle
3	Chicago
>>>
```

### <h3 id="24">24 - Create Table With a Primary Key Constraint</h3>

[[Create Table With a Primary Key Constraint.udemy](https://www.udemy.com/the-complete-oracle-sql-certification-course/learn/v4/t/lecture/5491354?start=15)]

[[techonthenet.com](https://www.techonthenet.com/)]

```SQL
CREATE TABLE products
(
  product_id number not null,
  name varchar(50),
  product_cost number(5,2),
  product_retail number(5,2),
  product_type varchar(10),
  store_id number not null,

  CONSTRAINT product_pk PRIMARY KEY (product_id)

)

>>>
Table created.

0.06 seconds
>>>
```

```SQL
INSERT INTO products(product_id, name, product_cost, product_retail, product_type, store_id) VALUES (1001, 'Colgate Toothpaste', 2.25, 5.47, 'hygiene', 2);

--COMMIT;

INSERT INTO products(product_id, name, product_cost, product_retail, product_type, store_id) VALUES (1002, 'Colgate Toothpaste', 2.25, 5.47, 'hygiene', 2);

--COMMIT;

INSERT INTO products(product_id, name, product_cost, product_retail, product_type, store_id) VALUES (1003, 'Listerine Mouthwash', 1.75, 4.81, 'hygiene', 3);

--COMMIT;

SELECT * FROM products;

>>>
PRODUCT_ID	NAME	PRODUCT_COST	PRODUCT_RETAIL	PRODUCT_TYPE	STORE_ID
1001	Colgate Toothpaste	2.25	5.47	hygiene	2
1002	Colgate Toothpaste	2.25	5.47	hygiene	2
1003	Listerine Mouthwash	1.75	4.81	hygiene	3
>>>
```

### <h3 id="25">25 - Using ALTER to modify the tavle structure</h3>

[[Using ALTER to modify the tavle structure.udemy](https://www.udemy.com/the-complete-oracle-sql-certification-course/learn/v4/t/lecture/5527236?start=0)]

```SQL
INSERT INTO products VALUES (1011, '', 4.00, 8.00, 'Clothing', 3)

SELECT * FROM products;

>>>
PRODUCT_ID	NAME	PRODUCT_COST	PRODUCT_RETAIL	PRODUCT_TYPE	STORE_ID
1011	-	4	8	Clothing	3
1001	Colgate Toothpaste	2.25	5.47	hygiene	2
1002	Colgate Toothpaste	2.25	5.47	hygiene	2
1003	Listerine Mouthwash	1.75	4.81	hygiene	3
>>>
```

DELETE

```SQL
DELETE FROM products WHERE product_id = 1011

SELECT * FROM products;
>>>
PRODUCT_ID	NAME	PRODUCT_COST	PRODUCT_RETAIL	PRODUCT_TYPE	STORE_ID
1001	Colgate Toothpaste	2.25	5.47	hygiene	2
1002	Colgate Toothpaste	2.25	5.47	hygiene	2
1003	Listerine Mouthwash	1.75	4.81	hygiene	3
>>>
```

ALTER TABLE

```SQL
ALTER TABLE products MODIFY name varchar2(50) not null;

DESCRIBE products;  

>>>
Table	Column	Data Type	Length	Precision	Scale	Primary Key	Nullable	Default	Comment
PRODUCTS	PRODUCT_ID	NUMBER	22	-	-	1	-	-	-
 	NAME	VARCHAR2	50	-	-	-	-	-	-
 	PRODUCT_COST	NUMBER	-	5	2	-	nullable	-	-
 	PRODUCT_RETAIL	NUMBER	-	5	2	-	nullable	-	-
 	PRODUCT_TYPE	VARCHAR2	10	-	-	-	nullable	-	-
 	STORE_ID	NUMBER	22	-	-	-	-	-	-
>>>
```

```SQL
ALTER TABLE products
  RENAME COLUMN name TO product_name;
  
SELECT * FROM products;
>>>
PRODUCT_ID	PRODUCT_NAME	PRODUCT_COST	PRODUCT_RETAIL	PRODUCT_TYPE	STORE_ID
1001	Colgate Toothpaste	2.25	5.47	hygiene	2
1002	Colgate Toothpaste	2.25	5.47	hygiene	2
1003	Listerine Mouthwash	1.75	4.81	hygiene	3
>>>
```

### <h3 id='26'>26 - Create Table with SELECT + UPDATE Data</h3>

[[Create Table with SELECT + UPDATE Data.udemy]()]

```SQL

>>>

>>>
```

```SQL

>>>

>>>
```

```SQL

>>>

>>>
```

### <h3 id='27'>27 - DELETE, TRUNCATE, and DROP Commands</h3>

[[DELETE, TRUNCATE, and DROP Commands.udemy]()]

```SQL

>>>

>>>
```

```SQL

>>>

>>>
```

```SQL

>>>

>>>
```

### <h3 id='28'>28 - Working With Database Indexes (Newly Added)</h3>

[[Working With Database Indexes (Newly Added).udemy]()]

```SQL

>>>

>>>
```

```SQL

>>>

>>>
```

```SQL

>>>

>>>
```

### <h3 id='29'>29 - System Tables, Pseudo Columns & Deleting Duplicates (Newly Added)</h3>

[[System Tables, Pseudo Columns & Deleting Duplicates (Newly Added).udemy]()]

```SQL

>>>

>>>
```

```SQL

>>>

>>>
```

```SQL

>>>

>>>
```

### <h3 id='30'>30 - Views and Other Objects and Commands (Newly Added)</h3>

[[Views and Other Objects and Commands (Newly Added).udemy]()]

```SQL

>>>

>>>
```

```SQL

>>>

>>>
```

```SQL

>>>

>>>
```
