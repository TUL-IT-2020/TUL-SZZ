#SQL
# Množinové operace
- **sjednocení** - sjednocením množin A a B vznikne nová množina, která bude obsahovat všechny prvky z množiny A a také všechny prvky z množiny B
- **kartézský součin** - je množina, označená A x B, která obsahuje všechny uspořádané dvojice, ve kterých je první položka prvkem množiny A a druhá položka je prvkem množiny B; kartézský součin obsahuje všechny takové kombinace těchto prvků
- **rozdíl** - rozdílem dvou množin A a B chápeme takovou množinu, která bude obsahovat všechny prvky z A a zároveň nebude obsahovat žádný prvek z B
- **selekce** (restrikce) - je unární relační operace odpovídající výběru řádků z tabulky na základě nějakého kritéria
- **projekce** - je relační operace, která odpovídá výběru sloupců z tabulky (tedy se omezíme pouze na některé atributy)
- **přejmenování** - má formální význam a využívá se zejména v souvislosti s join pro přejmenování atributu A na B
### Zdroje:
- [Množinové operace](https://www.interval.cz/clanky/sql-skladani-dotazu/)

## MS SQL
V Microsoft SQL Serveru můžete provádět množinové operace pomocí klauzulí jako `UNION`, `INTERSECT`, a `EXCEPT`. Níže je soupis těchto operací a jejich použití:
### 1. `UNION` a `UNION ALL`

#### `UNION`
Kombinuje výsledky dvou dotazů a odstraňuje duplicity.

```sql
SELECT column1, column2 FROM table1 
UNION 
SELECT column1, column2 FROM table2;
```
#### `UNION ALL`
Kombinuje výsledky dvou dotazů a ponechává duplicity.

```sql
SELECT column1, column2 FROM table1 
UNION ALL 
SELECT column1, column2 FROM table2;
```
### 2. `INTERSECT`
Vrátí řádky, které jsou společné pro oba dotazy.

```sql
SELECT column1, column2 FROM table1 
INTERSECT 
SELECT column1, column2 FROM table2;
```
### 3. `EXCEPT`
Vrátí řádky z prvního dotazu, které nejsou ve výsledku druhého dotazu (množinový rozdíl).

```sql
SELECT column1, column2 FROM table1 
EXCEPT 
SELECT column1, column2 FROM table2;
```