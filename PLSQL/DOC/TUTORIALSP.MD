
[PL/SQL](https://www.tutorialspoint.com/plsql/index.htm)
======

* <a href='#01'>01 - Basic Syntax</a>
* <a href='#02'>02 - Data Types</a>
* <a href='#03'>03 - Variables</a>
* <a href='#04'>04 - Constants and Literals</a>

<h2 id="01">Basic Syntax</h2>

Basic Structure

```sql
DECLARE 
   <declarations section> 
BEGIN 
   <executable command(s)>
EXCEPTION 
   <exception handling> 
END;
```

Hello World

```sql
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

```sql
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

<h2 id="03">03 - Variables</h2>

<h2 id="04">04 - Constants and Literals</h2>
