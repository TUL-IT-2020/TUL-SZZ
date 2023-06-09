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

## Databázový model
![[Casandra.png]]

Keyspace:: udržuje Column families a replikační faktor (databáze v RDBMS)

Column family:: sdružuje řádky obsahující sloupce (tabulka  v RDBMS)
- Dvouúrovňové key-value úložiště bez nutného schématu
- “Mapa map”:
	- Vnější mapa:: Row key, určuje místo na uzlu
	- Vnitřní mapa:: Column Key, setříděné na jednom uzlu

![[Cassandra row.png]]

Row:: řádka definovaná pomocí Row key bez nutně dané struktury (řádek v RDBMS)
Column:: hodnota s názvem a timestamp (hodnota v RDBMS)
- Standard:: s jednou hodnotou
- Composite:: pro složené primární klíče
- Expiring:: s omezenou platností, po vypršení je hodnota vymazána
- Counter:: inkrementační čítač

## Distribuce dat
Replikace:
- Replikace se nastavuje na úrovni Keyspace
- Každý uzel spravuje část token ring (partition)
- Při zápisu určí partitioner hodnotu tokenu hashovací funkcí
- Primární replika se uloží na uzel spravující část token ringu, kam token spadá
- Podle replikačního faktoru se přidají další repliky

Typy partitionerů:
- MurMur3Partitioner: MurMur3 hash
- RandomPartitioner: MD5 hash
- ByteOrderPartitioner: na základě lexikálního pořadí bitů

Strategie dělení token ringu:
- Jednoduchá
	- Pro jediné datacentrum s globálním replikačním faktorem
	- Rozdělení mezi nodes za sebou po směru ručiček
	- Bez ohledu na topologii
- Síťová
	- Replikační faktor pro každé datacentrum
	- Každé datacentrum má vlastní token ring
	- Následující node se bere z jiného racku v daném datacentru

Komunikace mezi uzly:
- Gossip protokol
- Každý uzel posílá informace o sobě dalším 3 uzlům
- Rychlá reakce na problém (výpadek, přetížení...)

Koordinátor:
- Uzel, který obdrží request
- Vybírá jej Cassandra driver
- Řídí replikační proces (počet replikovací a strategie)
- Řídí úroveň konzistence (kolik uzlů musí potvrdit read/write request)
- ANY, ONE, …, QUORUM, ALL
- Immediate consistency:: ALL
- Eventual consistency:: ONE

Zachování konzistence:
- Read Repair:: pokud má uzel nekonzistentní data, po požadavku se pošle aktualizační požadavek
- Anti Entropy Node Repair:: pokud byl uzel dlouho nedostupný, opravný nástroj se sám dotáže na data ostatních uzlů
- Hinted Handoff:: pokud je uzel nedostupný, ostatní uzly si uloží hint a až zjistí, že uzel naskočil, pošlou mu informaci o zápisu
