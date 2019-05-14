
---

###### [改善](https://github.com/ttltrk/0C/blob/master/README.MD) - [.co.](https://github.com/ttltrk/PRG/blob/master/CODING.MD) - [manuals](https://github.com/ttltrk/PRG/blob/master/MAN.MD)

###### [MUM](https://github.com/ttltrk/PRG/blob/master/MUM.MD) - [M](https://github.com/ttltrk/ELSE/blob/master/M/M.MD) || [PY](https://github.com/ttltrk/PRG/blob/master/PY/DOC/PYF/PYF.MD) - [SQL](https://github.com/ttltrk/DB/blob/master/SQL/DOC/OSM/OSQLM/SQLM/SQLM.MD) - [UX](https://github.com/ttltrk/ELSE/blob/master/M/UX/UX.MD) || [ENG](https://github.com/ttltrk/ELSE/blob/master/LAN/ENG/LE.MD) - [DE](https://github.com/ttltrk/ELSE/blob/master/LAN/GER/DUO_GER.MD) - [SP](https://github.com/ttltrk/ELSE/blob/master/LAN/SP/SP.MD) || [Tools](https://github.com/ttltrk/ELSE/blob/master/M/TOOLS/TOOLS.MD)

---

<h3 id='^'>SELECT</h3>

---

```
The SELECT statement is used to select data from a database.
The data returned is stored in a result table, called the result-set.
```

<a href='#^'>^^^</a>

---

```sql
SELECT column1, column2, ...
FROM table_name;
```

<a href='#^'>^^^</a>

---

```sql
SELECT * FROM trk_test
```

```sql
1	"trk"	"ttl"	"Hlavna 5"	"TNO"
2	"doe"	"jon"	"CA"	"GS"
3	"ewong"	"samatha"	"SFR"	"Dallas"
5	"petofi"	"alex"	"var"	"bp"
6	"kawhi"	"leo"	"canada"	"toronto"
4	"bbking"	"bbe"	"hemp"	"ams"
```

<a href='#^'>^^^</a>

---

```sql
SELECT lastname, address FROM trk_test
```

```sql
"trk"	"Hlavna 5"
"doe"	"CA"
"ewong"	"SFR"
"petofi"	"var"
"kawhi"	"canada"
"bbking"	"hemp"
```

<a href='#^'>^^^</a>

---
