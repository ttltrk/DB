
PL/SQL
======

* Basic Syntax
* Data Types
* Variables
* Constants and Literals

<h2>Basic Syntax</h2>

```plsql
DECLARE 
   <declarations section> 
BEGIN 
   <executable command(s)>
EXCEPTION 
   <exception handling> 
END;
```

```plsql
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
