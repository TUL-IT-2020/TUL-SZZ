# Databázové systémy

> Databázové systémy – relační a objektový model dat, NoSQL databáze (typy škálování, teorém CAP).

## Databázové systémy
**databáze** = organizovaná kolekce dat

**DBS** (databázový systém) = **SŘBD** (systém řízení báze dat; nebo anglicky DBMS - database management system) + **DB** (databáze; data)

SŘBD typicky obsahuje:
- parser - převod dotazovacího jazyka (např. SQL) do strojové podoby
- optimalizátor - optimalizace výrazu z pohledu výkonu
- operator evaluator (vyhodnocovatel výrazů)
- plan executor (vykonavatel plánů) - plán je strojová podoba příkazu, která je vyhodnocená, optimalizovaná a připravená k provedení
- lock manager - správa zámků
- transaction manager - správa transakcí

### Základní modely DBS
- [Navigační databáze](https://en.wikipedia.org/wiki/Navigational_database) - [hiearchický model](https://en.wikipedia.org/wiki/Hierarchical_database_model), [síťový model](https://en.wikipedia.org/wiki/Network_model) a [grafový model](https://en.wikipedia.org/wiki/Graph_database)
- [Relační model](https://en.wikipedia.org/wiki/Relational_model)
- [Objektový model](https://en.wikipedia.org/wiki/Object_database)
- [Dokumentový model](https://en.wikipedia.org/wiki/Document-oriented_database)

## Konceptuální model
Koncepce návrhu databáze. Formalizuje požadavek zákazníka na formu použitelnou při návrhu. Výsledkem modelování DB je schéma ve formě diagramu (UML).
Na konceptuální úrovni je možné při modelování reality využít k vyjádření konceptuálního schématu konceptuální modely. Ty jsou 4:
- Hierarchický, 
- Síťový, 
- Entitně-relační,
- Objektový.

### Relační model dat - RMD
![[RMD - Relační model dat]]

### Modelování relačního modelu pomocí UML
![[RMD - Modelování relačního modelu pomocí UML digramu]]

### Objektový model dat - OMD
![[OMD - Objektový model dat]]

## Srovnání RMD a OMD
Relační model je jednoduchý a elegantní, ale je naprosto rozdílný od objektového modelu. Relační databáze nejsou navrhovány pro ukládání objektů a naprogramování rozhraní pro ukládání objektů v databázi je velmi složité. Relační databázové systémy jsou dobré pro řízení velkého množství dat, vyhledávání dat, ale poskytují nízkou podporu pro manipulaci s nimi. Jsou založeny na dvourozměrných tabulkách a vztahy mezi daty jsou vyjadřovány porovnáváním hodnot v nich uložených. Jazyky jako SQL umožňují tabulky propojit za běhu, aby vyjádřily vztah mezi daty.

Naproti tomu objektové modely jsou založeny na objektech, což jsou struktury, které kombinují daný kód a data. Objektové databázové systémy umožňují využití hostitelského objektového jazyka jako je třeba C++, Java přímo na objekty "v databázi"; tj. místo věčného přeskakování mezi jazykem aplikace (např. C) a dotazovacím jazykem (např. SQL) může programátor jednoduše používat objektový jazyk k vytváření a přístupu k metodám. Krátce řečeno, OMD jsou výborné pro manipulaci s daty. Pokud navíc opomeneme programátorskou stránku, dá se říct, že některé typy dotazů jsou efektivnější než v RMD díky dědičnosti a referencím. 

## NoSQL databáze
![[NoSQL databáze]]

## SŘBD vs. NoSQL
**SŘBD**
- strukturovaná a organizovaná data
- SQL, DML, DDL, ACID
- transakce, konzistence

**NoSQL**
- nemá deklarativní dotazovací jazyk
- nemá definované schéma
- ukládá dvojice klíč-hodnota; Uložení sloupců, dokumentů, grafů
- případná konzistence upřednostněna před ACID
- podpora nestrukturovaných a nepředvídatelných dat
- CAP teorém
- upřednostňují vysoký výkon, dostupnost a rozšiřitelnost

## Zdroje:
https://projekty.fs.vsb.cz/463/edubase/VY_01_044/Databázové%20systémy.pdf