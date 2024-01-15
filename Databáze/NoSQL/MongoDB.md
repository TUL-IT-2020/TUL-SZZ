#NoSQL 
# Mongo DB
V současnosti nejpopulárnější  dokumentová databáze. Hu**mongo**us data.
Cloud: Atlas
mají free verzi

## Charakteristika
Dokumenty ukládány ve formátu BSON. Mongo je CP podle [[CAP teorém|CAP]]. Nemá A - selhání mastera způsobí chvilkový výpadek. P zajišťuje [[Replikace|replikace]] databáze. Při výpadku mastera nejsou možné operace zápisu, než se zvolí nový. Databáze využívá pro horizontální škálování [[Sharding]].

### Výhody:
- flexibilní databáze
- ad-hoc dotazování
- vestavěné agregace
- horizontální škálování a sharding
- vysoká dostupnost
- rychlost

### Nevýhody:
- JOIN není podporován
- rychlost (špatně zvolené indexy)
- paměťová náročnost
- max velikost dokumentu: 16MB
- max vnoření dokumentů: 100

## Architektura

### Dokument
Volné schéma
Max velikost: 16MB
Data patřící k sobě jsou uložena v jenom dokumentu. 

### Kolekce
Seznam dokumentů, odpovídá relaci (tabulce). 

### Operace
Přístup podle schéma [[CRUD]].

![[Mongo - CRUD.PNG]]

### Volné schéma

embedded dokumenty 
Denormalizace
umožnují vazby:
- 1:1,
- 1:N.

reference
Potřeba normalizovaného datového modelu. Využití kdyý by vnořené dokumenty vytvářeli množství duplikátů.
Vazby:
- M:N

Join pomocí: lookup

#### Pevné schéma
Lze docílit pomocí validačního schématu.


## Ad-hoc dotazy
Dotazy neznámé při návrhu databáze.

Typy:
- hledání podle pole dokumentu
- rozsahové dotazy
- hledání podle regulárních výrazů

## Indexování
Umožnuje [[DBS - Indexování|indexování]].
Typy indexů:
- single field - index nad jedním polem
- compound - nad více poli, závisí na pořadí
- multikey
- text
- hashed

## Agregace
- Agragační roura (pipeline)
- [[MapReduce|map-reduce]] (využití JavaScript funkcí)
- jednoúčelová agregace (pro dokumenty v jedné kolekci)

### Agregační roura
Dokumenty jsou zpracovány postupně v krocích až do konečného výsledku. Založená na principu roury na zpracování dat. Dokumenty vstupují do víceúrovňové roury, která je transformuje na agregovaný výsledek. Každá fáze transformuje dokumetny pro další fázi roury. 

fáze:
- match
- group

různé fáze:
- filtrování
- transformace dokumentů
- shlukování a řazení podle specifických polí
- agregace obsahu polí
- použití operátorů (průměr, zřetězení řetězů)

![[group vs project.PNG]]

### Map-reduce
Využíví se JavaSriptových funkcí. Vstupem jsou dokumenty jedné kolekce. 

- map - mapuje kodnoty ke klíči
- reduce - agreguje namapované hodnoty

Postup:
1. Master přijme požadavek [[MapReduce|map-reduce]] od klienta.
2. Rozešle fuknci map všem ostatním uzlům. 
3. Uzly paralelně provádějí kód funkce map a vrazí masteru výsledky. 
4. Po obdržení výsledků provádí master nad daty funkci reduce. 
5. Master agreguje výsledky. 
6. Odpověď klientovy.

![[map-reduce mongo.PNG]]

### Jednoúčelová agregace
MongoDB poskytuje operace:
- db.collestion.count() - výpočet dokumentů v kolekci
- db.collection.estimatedDocumentCount() - vrazí počet dokumentů v kolekci
- db.collection.distinct() - vrací unikátní hodnoty pro dané pole

Agregují dokumenty z jedné kolekce. 

## Funkce:
`Date()`
