
Data Types
======

[<<<](https://github.com/ttltrk/DB/blob/master/PLSQL/DOC/BPSM/BPSM.MD)

---

Valid declaration

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

---
