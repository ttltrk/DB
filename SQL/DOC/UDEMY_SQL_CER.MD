
[The Complete Oracle SQL Certification Course](https://www.udemy.com/the-complete-oracle-sql-certification-course/learn/v4/content)
======

### Database Basics
  * <a href='#1'>Oracle Database Introduction & Basics of Tables</a>
  * <a href='#2'>Setting Up the SQL Development Environment</a>
  
### Single Table Queries
  * <a href='#3'>Retrieving Data Using the SELECT Clause</a>
  * <a href='#4'>Using the WHERE Clause</a>
  * <a href='#5'>Using Operators in the WHERE Clause</a>
  * <a href='#6'>Combining WHERE, AND & OR with Operators</a>
  * <a href='#7'>Query Filtering Continued BETWEEN, IN and NULL</a>
  * <a href='#8'>Query Filtering Conditions & Operator Precedence</a>
  * <a href='#9'>Ordering, Concatenating and Aliasing Query Results</a>

### Single Row Functions
  * <a href='#10'>Single Row Functions (SRF) & Using the Dual Table</a>
  * <a href='#11'>Using Functions in WHERE and Character Based SRFs</a>
  * <a href='#12'>Numeric and Date Data type SRFs</a>
  * <a href='#13'>Conversion SRFs & Date Formatting</a>
  
### Section 4

### Section 5

### Section 6

Database Basics
------

#### <h4 id='1'>Oracle Database Introduction & Basics of Tables</h4>

#### <h4 id='2'>Setting Up the SQL Development Environment</h4>

Single Table Queries
------

#### <h4 id='3'>Retrieving Data Using the SELECT Clause</h4>

#### <h4 id='4'>Using the WHERE Clause</h4>

#### <h4 id='5'>Using Operators in the WHERE Clause</h4>

WHERE

```SQL
--List Out, all the managers from EMP
SELECT * FROM EMP
WHERE JOB = 'MANAGER';
```

```SQL
--List Out, all the jobs without MANAGER from EMP
SELECT * FROM EMP
WHERE JOB != 'MANAGER';
```

```SQL
--List Out, all the salesman with salary 1500 from EMP
SELECT * FROM EMP
WHERE JOB = 'SALESMAN'
AND SAL = 1500;
```

```SQL
--List Out, all the salesman with salary less than 2500 from EMP
SELECT * FROM EMP
WHERE JOB = 'SALESMAN'
AND SAL < 2500;
```

```SQL
--List Out, all the salesman with salary less than or equal to 3000 from EMP
SELECT * FROM EMP
WHERE JOB = 'SALESMAN'
AND SAL <= 3000;
```

```SQL
--Return the employees who have a comission greater than their salary
SELECT * FROM EMP
WHERE SAL < COMM;
```

```SQL
--Get all employees that are not managers and have sal greater than 2500 and also work in dep no#20
SELECT * FROM EMP
WHERE JOB != 'MANAGERS' 
AND SAL > 2500
AND DEPTNO = 20;
```

#### <h4 id='6'>Combining WHERE, AND & OR with Operators</h4>

OR

```SQL
--Get all employees that are clerks and salesmans.
SELECT * FROM EMP
WHERE JOB='CLERK'
OR JOB='SALESMAN';
```

AND

```SQL
--Get the names of those employees that are not managers nor salesman and have a salary greater than or
--equal to 2000
SELECT * FROM EMP
WHERE JOB != 'MANAGER'
AND JOB !='SALESMAN'
AND SAL >= 2000;
```
#### <h4 id='7'>Query Filtering Continued BETWEEN, IN and NULL</h4>

IN

```SQL
--Get the names of the employees that works in Dallas and in Chicago
SELECT ename, hiredate, deptno FROM EMP
WHERE DEPTNO IN (20, 30);
```

```SQL
--get the mentioned names
SELECT ename, hiredate
FROM EMP
WHERE ENAME IN ('FORD', 'SMITH');
```

NOT IN

```SQL
get all the names without the selected ones
SELECT ename, hiredate
FROM EMP
WHERE ENAME NOT IN ('FORD', 'SMITH');
```

BETWEEN

```SQL
--between the selected range
SELECT * FROM EMP
WHERE hiredate 
BETWEEN '05/01/1981' AND '01/12/1983';
```

NOT BETWEEN

```SQL
SELECT * FROM EMP
WHERE SAL 
NOT BETWEEN 1000 AND 2000;
```

NULL

```SQL
--records with no data
SELECT * FROM EMP
WHERE COMM IS NULL;
```

NOT NULL

```SQL
SELECT * FROM EMP
WHERE COMM IS NOT NULL;
```

#### <h4 id='8'>Query Filtering Conditions & Operator Precedence</h4>

```SQL
-- all employees with null and 0 in COMM and SAL is in the range 1100-5000 and not equal to 1500
SELECT * FROM EMP
WHERE (COMM IS NULL OR COMM = 0)
AND SAL > 1100 
AND SAL < 5000
AND SAL <> 1500;
```

```SQL
-- all salesman with comm 300 and more than 1000
SELECT * FROM EMP
WHERE JOB = 'SALESMAN'
AND (COMM = 300 OR COMM > 1000);
```
#### <h4 id='9'>Ordering, Concatenating and Aliasing Query Results</h4>

```SQL
--return back the ENAME as EMPLOYEE NAME, SAL as SALARY and COMM as COMMISION
SELECT ENAME "EMPLOYEE NAME", SAL SALARY, COMM COMMISION
FROM EMP;
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

#### <h4 id='10'>Single Row Functions (SRF) & Using the Dual Table</h4>

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

```SQL
SELECT concat('my name is ', ename) as sentence
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
SELECT concat(lower(ename), ' is the name') AS name
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
SELECT concat(lower(ename), upper(' is the name')) AS name
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
SELECT concat (concat (lower(ename), upper(' is the name ') ), concat ('and their job is: ', job ) ) AS MAIN
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

#### <h4 id='11'>Using Functions in WHERE and Character Based SRFs</h4>

```SQL
SELECT JOB FROM emp
WHERE job = lower('MANAGER');

>>>
np data found
>>>
```

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

```SQL
SELECT initcap ('hello world') as hello
FROM DUAL;

>>>
HELLO
Hello World
>>>
```

```SQL
SELECT length ('hello world') as hello
FROM DUAL;

>>>
11
>>>
```

```SQL
SELECT length (ename) as length
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
SELECT ename, length (ename) as length
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
SELECT ename, length (ename) as length
FROM emp
WHERE length (ename) = 6;

>>>
ENAME	LENGTH
MARTIN	6
TURNER	6
MILLER	6
>>>
```

```SQL
SELECT 'hello', substr ('hello', 2, 2) as substring
FROM DUAL;

>>>
'HELLO'	SUBSTRING
hello	el
>>>
```

```SQL
SELECT 'hello', substr ('hello', 2) as substring
FROM DUAL;

>>>
'HELLO'	SUBSTRING
hello	ello
>>>
```

```SQL
SELECT LPAD ('hello', 10, '&') as LPAD
FROM DUAL;

>>>
LPAD
&&&&&hello
>>>
```

```SQL
SELECT RPAD ('hello', 10, '&') as RPAD
FROM DUAL;

>>>
RPAD
hello&&&&&
>>>
```

```SQL
SELECT LTRIM ('hello','h') as LTRIM
FROM DUAL;

>>>
LTRIM
ello
>>>
```

```SQL
SELECT RTRIM ('hello','o') as RTRIM
FROM DUAL;

>>>
RTRIM
hell
>>>
```

#### <h4 id='12'>Numeric and Date Data type SRFs</h4>

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

#### <h4 id='13'>Conversion SRFs & Date Formatting</h4>

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

