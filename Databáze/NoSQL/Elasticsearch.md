# ElasticSearch
Distribuovaný open-source fulltext vyhledávač
Využití:
- Vyhledávač – indexace
- Logování a analytika
- Metriky a monitorování kontejnerů
- Business analytika

Hlavní komponenta Elastic Stacku
- ElasticSearch:: ukládání a vyhledávání
- Kibana:: vizualizace
- Logstash:: agregace a zpracování dat pro uložení do ElasticSearch

![[ElasticSearch.png]]

Koncepty
- Dokument:: JSON jednotka informací s unikátním ID a datovým typem
- Index:: kolekce souvisejících dokumentů v jejímž rámci lze vyhledávat
- Invertovaný index:: struktura pro rychlé fulltextové vyhledávání
	- Index jedinečných slov, která se objevují v celém setu dokumentů
	- Identifikuje všechny dokumenty, kde se toto slovo nachází (jako ve VWM)

## Architektura
Node:: jedna instance ElasticSearch
Master:: spravuje indexy a nodes
Data node:: ukládá data, vyhledává a agreguje
Client node:: přeposílá požadavky masterovi a na data nodes
Cluster:: skupina propojených nodes
Shard:: část indexu, implementuje redundanci
Replica:: duplikát primary shardu
