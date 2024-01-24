#SQL
# Spojení tabulek
![[SQL_joins.png]]
**přirozené spojení**
``` sql
SELECT * FROM R NATURAL JOIN S;
```
**spojení křížem (kartézský součin)**
``` sql
SELECT * FROM R CROSS JOIN S;
```
**spojení přes podmínku**
``` sql
SELECT * FROM R JOIN S ON A > B;
```
**spojení přes vyjmenované sloupce**
``` sql
SELECT * FROM R JOIN S USING (A, B);
```
**vnitřní vs. vnější spojení**
Vnější spojení slouží k přidání některých řádků, které se s ničím nespojily, do výsledku.
``` sql
SELECT * FROM R INNER(LEFT, RIGHT) JOIN S USING (A, B);
```

![[JOIN_1.jpeg]]
![[JOIN_2.jpeg]]