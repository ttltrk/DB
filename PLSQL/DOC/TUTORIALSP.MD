
[PL/SQL](https://www.tutorialspoint.com/plsql/index.htm)
======

* <a href='#01'>01 - Basic Syntax</a>
* <a href='#02'>02 - Data Types</a>
* <a href='#03'>03 - Variables</a>
* <a href='#04'>04 - Constants and Literals</a>

<h2 id="01">Basic Syntax</h2>

Basic Structure

```
DECLARE 
   <declarations section> 
BEGIN 
   <executable command(s)>
EXCEPTION 
   <exception handling> 
END;
```

Hello World

```
DECLARE 
   message  varchar2(20):= 'Hello, World!'; 
BEGIN 
   dbms_output.put_line(message); 
END; 
/ 

>>>
Hello World  

PL/SQL procedure successfully completed.
>>>
```

Comments

```
DECLARE 
   -- variable declaration 
   message  varchar2(20):= 'Hello, World!'; 
BEGIN 
   /* 
   *  PL/SQL executable statement(s) 
   */ 
   dbms_output.put_line(message); 
END; 
/

>>>
Hello World

PL/SQL procedure successfully completed.
>>>
```

PL/SQL Program Units

  * PL/SQL block
  * Function
  * Package
  * Package body
  * Procedure
  * Trigger
  * Type
  * Type body
    
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

<h2 id="04">04 - Constants and Literals</h2>
