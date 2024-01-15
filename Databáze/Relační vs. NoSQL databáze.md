#SQL 
#NoSQL
# Srovnání Relačních a NoSQL databází
NoSQL se nesnaží nahradit relační DBS. 

![[SQL vs NoSQL.PNG]]

### NoSQL
Zpracování velkých objemů vzájemně nesouvisejících nebo rychle se měněních dat. Data nezávislá na schématu. Aplikace preferující výkon a dostupnost před silnou konzistencí. Neustále přístupné aplikace slouží uživatelům po celém světě. 

Nerelační databáze (žádné relace). Vyhýbají se vazbám mezi daty. Distribuované databáze.

Hierarchické ukládání dat (klíč-hodnota).

Nemají jednotný jazyk. Realizace složitějších dotazů je velice obtížná.


- nemá deklarativní dotazovací jazyk
- nemá definované schéma
- ukládá dvojice klíč-hodnota; Uložení sloupců, dokumentů, grafů
- případná konzistence upřednostněna před ACID
- podpora nestrukturovaných a nepředvídatelných dat
- CAP teorém
- upřednostňují vysoký výkon, dostupnost a rozšiřitelnost

#### Použití:
- mobilní aplikace
- analýza v reálném čase
- správa obsahu
- IoT

### Relační DBS
Zpracování relačních dat mající logické a diskrétní požadavky určené předem. Starší systémy pro relační struktury. Aplikace vyžadující komplexní dotazování nebo transakce s více řádky. Staví na [[SQL - ACID|ACID]] vlastnostech transakcí. 

- strukturovaná a organizovaná data
	- definované relace (tabulky)
	- atributy (sloupce)
	- vazby mezi relacemi
- SQL, DML, DDL, ACID
- transakce, konzistence

Data ukládaná ve formě záznamu (řádků) v relacích. Související data jsou mnohdy uložená odděleně. Pomocí dotazů je spojujeme. Modelují vztahy mezi daty.

Využívá se jazyka [[Jazyk SQL|SQL]].

Relační databáze jsou dlouhodobě zažitá a používaná technologie.

#### Použití:
- účetnictví, bankovnictví
- řízení zásob