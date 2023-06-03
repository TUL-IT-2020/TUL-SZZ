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

## Relační model dat - RMD
![[RMD - Relační model dat]]

## Objektový model dat - OMD
Objektová databáze je systém správy databází, ve kterém je informace reprezentována formou objektů. To by mělo přirozeněji a věrněji popisovat
skutečný svět a entity modelované v databázi. Lze je rozdělit na **objektově orientované** a **objektově relační**. Objektově orientované jsou si podobné s objekty v objektově orientovaných programovacích jazycích. Pro obě skupiny neexistuje žádný standard. V praktickém využití jej nalezneme minimálně oproti relačnímu modelu.

### Objektově orientovaný datový model
OOSŘBD využívají datového modelu, který má objektově orientované aspekty jako třídy s atributy a metodami a integritními omezeními; poskytují objektové identifikátory (OID) pro každou trvalou instanci třídy; podporují zapouzdření (encapsulation); násobnou dědičnost (multiple inheritance) a podporují abstraktní datové typy.

Kombinují prvky objektově orientovaného programování s databázovými schopnostmi. Rozšiřují funkčnost objektových programovacích jazyků (C++, Java) a poskytují plnou schopnost programování databáze. Datový model aplikace a datový model databáze se ve výsledku hodně shodují a výsledný kód se dá mnohem efektivněji udržovat. Objektově orientovaný jazyk (C++, Java) je jazykem jak pro aplikaci, tak i pro databázi. Poskytuje těsný vztah mezi objektem aplikace a uloženým objektem.

### Objektově relační datový model
ORSŘBD využívají datový model tak, že "přidávají objektovost do tabulek". Všechny trvalé informace jsou stále v tabulkách, ale některé položky mohou mít bohatší datovou strukturu, nazývanou abstraktní datové typy (ADT). ADT je datový typ, který vznikne zkombinováním základních datových typů. Podpora ADT je atraktivní, protože operace a funkce asociované s novými datovými typy mohou být použity k indexování, ukládání a získávání záznamů na základě obsahu nového datového typu.

## Srovnání RMD a OMD
Relační model je jednoduchý a elegantní, ale je naprosto rozdílný od objektového modelu. Relační databáze nejsou navrhovány pro ukládání objektů a naprogramování rozhraní pro ukládání objektů v databázi je velmi složité. Relační databázové systémy jsou dobré pro řízení velkého množství dat, vyhledávání dat, ale poskytují nízkou podporu pro manipulaci s nimi. Jsou založeny na dvourozměrných tabulkách a vztahy mezi daty jsou vyjadřovány porovnáváním hodnot v nich uložených. Jazyky jako SQL umožňují tabulky propojit za běhu, aby vyjádřily vztah mezi daty.

Naproti tomu objektové modely jsou založeny na objektech, což jsou struktury, které kombinují daný kód a data. Objektové databázové systémy umožňují využití hostitelského objektového jazyka jako je třeba C++, Java přímo na objekty "v databázi"; tj. místo věčného přeskakování mezi jazykem aplikace (např. C) a dotazovacím jazykem (např. SQL) může programátor jednoduše používat objektový jazyk k vytváření a přístupu k metodám. Krátce řečeno, OMD jsou výborné pro manipulaci s daty. Pokud navíc opomeneme programátorskou stránku, dá se říct, že některé typy dotazů jsou efektivnější než v RMD díky dědičnosti a referencím. 

## NoSQL databáze
![[NoSQL databáze]]

## SŘBD vs. NoSQL
SŘBD
- strukturovaná a organizovaná data
- SQL, DML, DDL, ACID
- transakce, konzistence

NoSQL
- nemá deklarativní dotazovací jazyk
- nemá definované schéma
- ukládá dvojice klíč-hodnota; Uložení sloupců, dokumentů, grafů
- případná konzistence upřednostněna před ACID
- podpora nestrukturovaných a nepředvídatelných dat
- CAP teorém
- upřednostňují vysoký výkon, dostupnost a rozšiřitelnost
