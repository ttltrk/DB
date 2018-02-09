
PL/SQL
======

* Basic Syntax
* Data Types
* Variables
* Constants and Literals

<h2>Basic Syntax</h2>

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
