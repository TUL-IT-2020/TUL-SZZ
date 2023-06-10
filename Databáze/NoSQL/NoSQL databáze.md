# NoSQL databáze
**NoSQL** = Not only SQL database

NoSQL je nerelační systém řízení báze dat navržený pro distribuovaná datová uložiště, nevyžadující pevné předem definované schéma databáze, nepoužívající JOIN operace a horizontálně [[Škálování|škálují]] (při větším vytížení stačí přidat další instanci). 

## Distribuovaná databáze 
Systém, který je složen z několika počítačů a softwarových komponent, které spolu komunikují pomocí počítačové sítě.

Výhody:
- spolehlivost - pokud některý uzel má výpadek, tak to neohrozí funkci celého systému,
- rozšiřitelnost - distribuovaný systém je možné snadno rozšířit přidáním nových serverů,
- sdílení zdrojů - je základní pro mnoho aplikací, data jsou sdílena v distribuovaném systému,
- flexibilita - je snadnější instalovat, implementovat a odladit nové služby,
- rychlost, výkon.

Nevýhody:
- závislost na počítačové síti,
- obecně složitější na správu,
- obecně méně bezpečné než autonomní systémy.

## CAP teorém
![[CAP teorém]]

## Typy NoSQL databází:
- [[Key-value uložiště|key-value uložiště]]
- [[Dokumentové databáze|dokumentové databáze]] ([[MongoDB]], [[Elasticsearch]])
- sloupcová uložiště ([[Cassandra]])
- grafová uložiště
- databáze časových řad

![[NoSQL.jpeg]]

![[truth-of-cap-theorem-diagram.webp]]

## Struktura dat
- strukturovaná data
- částečně strukturovaná data
- nestrukturovaná

### Volné schéma
Žádné předdefinované nastavení -> flexibilita.

## Indexování
Vylepšuje rychlost vyhledávání. Bez indexování se provádí sken celé databáze. Vhodný index výrazně omezuje rozsah, který je potřeba skenovat. 

### Index
Speciální datová struktura definovaná na úrovni setů, polí, kolekcí. Obsahují ukazatel na data. Ukládá hodnotu specifického pole v seřazené formě. Využití i pro rychlé řazení. Základ pro 
[[Sharding|sharding]].

Vylepšuje rychlost vyhledávání. 
Vkládání prvků vynutí aktualizaci indexu a ta je pomalá, proto není vhodné mít mnoho indexů. 

## Replikace
Automatická distribuce změn v originále do jeho kopií. 
Zajištuje vysokou dostupnost.

## Srovnání s relačními databázemi
NoSQL se nesnaží nahradit ralační DBS. 

![[SQL vs NoSQL.PNG]]

### NoSQL
Zpracování velkých objemů vzájemně nesouvisejících nebo rychle se měněních dat. Data nezávislá na schématu. Aplikace preferující výkon a dostupnost před silnou konzistencí. Neustále přístupné aplikace slouží uživatelům po celém světě. 

Nerelační databáze (žádné relace). Vyhýbají se vazbám mezi daty. Distribuované databáze.

Hierarchické ukládání dat (klíč-hodnota).

Nemají jednotný jazyk. Realizace složitějších dotazů je velice obtížná.

#### Použití:
- mobilní aplikace
- analýza v reálném čase
- správa obsahu
- IoT

### Relační DBS
Zpracování relačních dat mající logické a diskrétní požadavky určené předem. Starší systémy pro relační struktury. Aplikace vyžadující komplexní dotazování nebo transakce s více řádky. Staví na [[SQL - ACID|ACID]] vlastnostech transakcí. 

- definované relace (tabulky)
- atributy (sloupce)
- vazby mezi relacemi

Data ukládaná ve formě záznamu (řádků) v relacích. Související data jsou mnohdy uložená odděleně. Pomocí dotazů je spojujeme. Modelují vztahy mezi daty.

Využívá se jazyka [[Jazyk SQL|SQL]].

Relační databáze jsou dlouhodobě zažitá a používaná technologie.

#### Použití:
- účetnictví, bankovnictví
- řízení zásob
