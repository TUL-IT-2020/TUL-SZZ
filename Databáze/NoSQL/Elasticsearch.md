# ElasticSearch
Distribuovaný open-source fulltext vyhledávač.
Využití:
- Vyhledávač – indexace
- Logování a analytika
- Metriky a monitorování kontejnerů
- Business analytika
- Automatické doplňování
- Autokorekce

## Elastic Stack
Hlavní komponenty Elastic Stacku:
- **ElasticSearch**: ukládání a vyhledávání
- **Kibana**: vizualizace a analýza dat
- **Logstash**: (roura) agregace a zpracování dat pro uložení do ElasticSearch

![[ElasticSearch.png]]

## Architektura
- **Node**: jedna instance ElasticSearch 
	- **Data node**: ukládá data, vyhledává a agreguje
	- **Client node**: přeposílá požadavky masterovi a na data nodes
- **Master**: spravuje indexy a nodes
- **Cluster**: skupina propojených nodes
- **Shard**: část indexu, implementuje redundanci
	- **Replica**: duplikát primary shardu

### Uzle
- master - řídí tvorbu indexů, přiřazuje shardy. 
- data - ukládá data, dotazy nad daty.
- ingres - pipiline, krokry při indexaci dokumentů. 

Role uzlů:
- machine learning - možnost provádět úlohy strojového učení.
- coordination - distribuce dotazů a agregace výsledků.
- voting_only - účsatní se volby mastera, sám jím být nemůže. 

### Základní koncepty
- Dokument: JSON jednotka informací s unikátním ID a datovým typem
- Index: kolekce souvisejících dokumentů v jejímž rámci lze vyhledávat
- Invertovaný index: struktura pro rychlé fulltextové vyhledávání
	- Index jedinečných slov, která se objevují v celém setu dokumentů
	- Identifikuje všechny dokumenty, kde se toto slovo nachází (jako ve VWM)

Jednotlivé dotazy jsou spouštěny nad indexy.

## Prohledávání 
Dva způsoby psaní vyhledávacích dotazů:
- Request UI
- Query DSL

Hlavní výsledek hledání:
- total - počet dokumentů odpovídajících hledání
- max_score - maximální skére relevance
- hits - pole výsledků

Relevance vyjadřuje jakou měrou výsledek odpovídá dotazu.

Kontext dotazů:
- query context - dotazovací kontext: "Jak moc dokumenty odpovídají dotazu?"
- filter context - filtrovací kontext: "Vyhovují dikumenty dotazu?"

Dotazovací typy:
- term level queries (vyhledává se přesná hodnoty)
- full-text queries 

### Full-text
- match query (vyhledávání na google)
- match_phrase 
- multi_match (přes více polí)

- leaf queries (koncové jednoduché dotazy)
- compound querues
- bool query

### Spojování dotazů
Ukládání dat v Elasticsearch odpovídá NoSQL databázím ne relačním databázím.
Dokumenty jsou demoralizovány. Omezená podpora join operací.

- nested query
- nested inner hits
- 

### Algoritmy:
- [[TF-IDF|TF/IDF]] (Term * Frequency / Inverse Document Frequency)
- [[BM25|Okapi BM25]]

## Analýza
Tokeny jsou uložené v [[indexování|invertovaném indexu]]. Invertované indexy jsou vytvářeny pro každé textové pole. 

### Analyzér

Složení:
- znakový filter
- tokenizér
- token filter

#### Character filters
Odstranění:
- html značek
- diakritiky

#### Tokenizer
Rozdělní řetězce na tokeny.
Převod stringu na pole.

#### Token filters
Mohou přidávat, modifikovat, nebo mazat tokeny. 

- lowercase filter

## Mapování datových typů
Dva typy:
- explicitní (manuální nastavení polí a jejich datovýc htypů)
- dynamické (sám rozhodne co se bude mapovat)

### Datové typy:
- boolen, short, integer, long, float, double, date
- object (JSON objekt)
- nested (object zachovávající vztahy mezi objekty)
- text (full textové vyhledávání)
- keyword (nutná přesná shoda při vyhledávání)

## Agregace
Dvě kategorie:
- single-value numeric
- multi-value numeric

"aggs"

metriky:
- cardinality - počet unikáních hodnot
- value_count
- stats

Bucket agregate

## Sharding
Každý [[Sharding|shard]] slouží jako samostatný index. Může obsahovat až 2 miliardy dokumentů. V základu má každý index jeden shard. 

Routing
`shard_num = hash(_routing) % num_primary_shards`
- `_routing` - id dokumentu
Zajištuje rovnoměrní rozmístění dokumentů mezi shardy. 