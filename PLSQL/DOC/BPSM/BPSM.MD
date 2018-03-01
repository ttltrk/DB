
Basic PLSQL Manual (BPSM)
======

[<<<](https://github.com/ttltrk/PRG/blob/master/MANUALS.MD)

---

* <a href='#01'>01 - Basic Syntax</a>
* <a href='#02'>02 - Data Types</a>
* <a href='#03'>03 - Variables</a>
* <a href='#04'>04 - Constants and Literals</a>
* <a href='#05'>05 - Operators</a>
* <a href='#06'>06 - Conditions</a>
* <a href='#07'>07 - Loops</a>
* <a href='#08'>08 - Strings</a>
* <a href='#09'>09 - Arrays</a>
* <a href='#10'>10 - Procedures</a>
* <a href='#11'>11 - Functions</a>
* <a href='#12'>12 - Cursors</a>
* <a href='#13'>13 - Records</a>
* <a href='#14'>14 - Exceptions</a>
* <a href='#15'>15 - Triggers</a>
* <a href='#16'>16 - Packages</a>
* <a href='#17'>17 - Collections</a>
* <a href='#18'>18 - Transactions</a>
* <a href='#19'>19 - Date & Time</a>
* <a href='#20'>20 - DBMS Output</a>
* <a href='#21'>21 - Object Oriented</a>

---

[tutorialspoint.com](https://www.tutorialspoint.com/plsql/index.htm)

---
 
<h2 id="02">02 - Data Types</h2>

valid declaration

```
DECLARE 
   num1 INTEGER; 
   num2 REAL; 
   num3 DOUBLE PRECISION; 
BEGIN 
   null; 
END; 
/ 

>>>
PL/SQL procedure successfully completed 
>>>
```

```
DECLARE 
   SUBTYPE name IS char(20); 
   SUBTYPE message IS varchar2(100); 
   salutation name; 
   greetings message; 
BEGIN 
   salutation := 'Reader '; 
   greetings := 'Welcome to the World of PL/SQL'; 
   dbms_output.put_line('Hello ' || salutation || greetings); 
END; 
/ 

>>>
Hello Reader Welcome to the World of PL/SQL 
 
PL/SQL procedure successfully completed.
>>>
```

<h2 id="03">03 - Variables</h2>

```
DECLARE 
   a integer := 10; 
   b integer := 20; 
   c integer; 
   f real; 
BEGIN 
   c := a + b; 
   dbms_output.put_line('Value of c: ' || c); 
   f := 70.0/3.0; 
   dbms_output.put_line('Value of f: ' || f); 
END; 
/  

>>>
Value of c: 30 
Value of f: 23.333333333333333333  

PL/SQL procedure successfully completed. 
>>>
```

```
DECLARE 
   -- Global variables  
   num1 number := 95;  
   num2 number := 85;  
BEGIN  
   dbms_output.put_line('Outer Variable num1: ' || num1); 
   dbms_output.put_line('Outer Variable num2: ' || num2); 
   DECLARE  
      -- Local variables 
      num1 number := 195;  
      num2 number := 185;  
   BEGIN  
      dbms_output.put_line('Inner Variable num1: ' || num1); 
      dbms_output.put_line('Inner Variable num2: ' || num2); 
   END;  
END; 
/ 

>>>
Outer Variable num1: 95 
Outer Variable num2: 85 
Inner Variable num1: 195 
Inner Variable num2: 185  

PL/SQL procedure successfully completed. 
>>>
```

PT1

```
CREATE TABLE CUSTOMERS( 
   ID   INT NOT NULL, 
   NAME VARCHAR (20) NOT NULL, 
   AGE INT NOT NULL, 
   ADDRESS CHAR (25), 
   SALARY   DECIMAL (18, 2),        
   PRIMARY KEY (ID) 
);  

>>>
Table Created  
>>>
```

PT2

```
INSERT INTO CUSTOMERS (ID,NAME,AGE,ADDRESS,SALARY) 
VALUES (1, 'Ramesh', 32, 'Ahmedabad', 2000.00 );  

INSERT INTO CUSTOMERS (ID,NAME,AGE,ADDRESS,SALARY) 
VALUES (2, 'Khilan', 25, 'Delhi', 1500.00 );  

INSERT INTO CUSTOMERS (ID,NAME,AGE,ADDRESS,SALARY) 
VALUES (3, 'kaushik', 23, 'Kota', 2000.00 );
  
INSERT INTO CUSTOMERS (ID,NAME,AGE,ADDRESS,SALARY) 
VALUES (4, 'Chaitali', 25, 'Mumbai', 6500.00 ); 
 
INSERT INTO CUSTOMERS (ID,NAME,AGE,ADDRESS,SALARY) 
VALUES (5, 'Hardik', 27, 'Bhopal', 8500.00 );  

INSERT INTO CUSTOMERS (ID,NAME,AGE,ADDRESS,SALARY) 
VALUES (6, 'Komal', 22, 'MP', 4500.00 ); 
```

PT3

```
DECLARE 
   c_id customers.id%type := 1; 
   c_name  customers.name%type; 
   c_addr customers.address%type; 
   c_sal  customers.salary%type; 
BEGIN 
   SELECT name, address, salary INTO c_name, c_addr, c_sal 
   FROM customers 
   WHERE id = c_id;  
   dbms_output.put_line 
   ('Customer ' ||c_name || ' from ' || c_addr || ' earns ' || c_sal); 
END; 
/  

>>>
Customer Ramesh from Ahmedabad earns 2000  

PL/SQL procedure completed successfully
>>>
```

<h2 id="04">04 - Constants and Literals</h2>

<h2 id="05">05 - Operators</h2>

<h2 id="06">06 - Conditions</h2>

<h2 id="07">07 - Loops</h2>

<h2 id="08">08 - Strings</h2>

<h2 id="09">09 - Arrays</h2>

<h2 id="10">10 - Procedures</h2>

<h2 id="11">11 - Functions</h2>

<h2 id="12">12 - Cursors</h2>

<h2 id="13">13 - Records</h2>

<h2 id="14">14 - Exceptions</h2>

<h2 id="15">15 - Triggers</h2>

<h2 id="16">16 - Packages</h2>

<h2 id="17">17 - Collections</h2>

<h2 id="18">18 - Transactions</h2>

<h2 id="19">19 - Date & Time</h2>

<h2 id="20">20 - DBMS Output</h2>

<h2 id="21">21 - Object Oriented</h2>


