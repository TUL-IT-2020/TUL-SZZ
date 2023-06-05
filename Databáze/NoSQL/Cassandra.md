# Apache Cassandra
## Úvod do Apache Cassandra
NoSQL databáze stavějící na vlastnostech AP systém podle [[CAP teorém|CAP teorému]]. Open source distribuovaný databázový systém. 

### Principy:
- Denormalizace - absence JOIN operací.
- Datová redundance - zapisujeme tak, jak chceme číst.
- Součástí Wide-Column family - rozrůstá se do šířky, ne do délky. 
- Implementace ukládání stylem hodnota-klíč, to z Cassandra dělá “fancy hash table”.

### Základní funkce:
Replikace: systém sám replikuje podle zadaných kritérií
Transparentní škálování (stejný kód pro 1 i 100 uzlů)
Nastavitelná konzistence pro jednotlivé dotazy, i za běhu aplikace.
Nastavitelná síťová strategie - ukládání dat do jednotlivých racků a datacenter
Cassandra Query Language (CQL) - podobné SQL
Postavené na [[MapReduce|MapReduce]]: podpora Hadoop MapReduce.

## Architektura
- **Node**:: jedna instance Cassandry
	- CommitLog
		- Log změn od posledního flushe do SSTable
		- Na disku pro případ výpadku RAM
	- Memtables
		- tabulková struktura v RAM pro rychlý zápis
		- Flushuje se do SSTable (rychlý zápis)
	- SSTables:: trvale uložené snapshoty Memtables
	- Při čtení se kouká do Memtables, poté podle Bloom filteru do SSTables

- **Partition** (segment):: seřazená a replikovatelná skupina dat v node
- **Rack**:: logická množina nodes
- **Datacenter**:: množina racků
- **Token**:: ID řádky vytvořené z jejího klíče (Row key)
- **Token ring**:: interval všech možných tokenů, jehož správa je rozdělena mezi uzly
- **Cluster**:: úplná množina nodes, která se mapuje na kompletní Token ring
