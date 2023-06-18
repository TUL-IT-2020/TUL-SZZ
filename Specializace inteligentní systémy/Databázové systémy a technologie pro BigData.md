#### Databázové systémy a technologie pro BigData:

27. Architektura relačních [[Databazove_systemy#Databázové systémy|databázových systémů]], [[Databazove_systemy#Konceptuální model|datový model]], [[RMD - Modelování relačního modelu pomocí UML digramu|konceptuální modelování]].
28. [[RMD - Relační model dat|Relační model]], [[RMD - Relační model dat#Základní pojmy|základní konstrukty]], [[RMD - Relační model dat#Vztah|realizace vztahů v relačním modelu]], [[RMD - Relační model dat#Integrita databáze a integritní omezení|integritní omezení]]. 
	- [[Mormalizace_BDS|Normalizace]], [[RMD - Normalizace|normální formy]], [[RMD - Funkční závislosti|funkční závislosti]], [[RMD - Návrhové anomálie|aktualizační anomálie]]. 
29. [[Jazyk SQL|Jazyk SQL]] - [[Jazyk SQL#DML / [SELECT](https //cs.wikipedia.org/wiki/SELECT)|selekce]], projekce, [[Agregační funkce|agregační funkce]], [[SQL - Množinové operace|množinové operace]], [[SQL - Spojení tabulek|typy spojení]], vnořené dotazy, [[Uložené procedury a spouště (od SQL3)|spouště a uložené procedury]]. 
30. [[SQL - Transakce|Transakce]] - koncept a vlastnosti transakcí ([[SQL - ACID|ACID]]). 
31. [[BigData|BigData]] - definice, dělení podle [[BigData#Struktura Dat|struktury]] a [[BigData#Odkud Big Data pochází?|původu]], [[BigData#Charakteristiky Big Data|charakteristika]], [[BigData#Aplikace Big Data|aplikace]]. 
	- [[BigData#Analýza velkých dat|Analýza velkých dat]] - jednotlivé kroky, typy, výhody a výzvy. 
32. [[NoSQL databáze|NoSQL databáze]] - koncept, vlastnosti, [[NoSQL databáze#Typy NoSQL databází|dělení]], [[Relační vs. NoSQL databáze|srovnání]] s relačními databázemi. Pojmy: [[NoSQL databáze#Volné schéma|volné schéma]], [[CAP teorém|CAP teorém]], [[DBS - Indexování|indexování]], [[NoSQL databáze#Agregace|agregace]], [[Replikace|replikace]], [[Škálování|škálování]], [[Sharding|sharding]]. 
33. [[Dokumentové databáze|Dokumentové databáze]] - koncept, srovnání s [[Key-value uložiště|key-value úložišti]], pojem [[Dokumentové databáze#Dokument|dokument]], výhody a nevýhody. 
	- [[MongoDB|MongoDB]] - [[MongoDB#Charakteristika|charakteristika]] a [[MongoDB#Architektura|architektura]]. 
34. [[Databáze pro prohledávání|Databáze pro prohledávání]] a analýzu textu - princip, vlastnosti. 
	- [[Elasticsearch|Elasticsearch]] - [[Elasticsearch#Architektura|architektura]], [[Elasticsearch#Prohledávání|prohledávání]] vs. [[Elasticsearch#Analýza|analýza]], [[indexování|invertovaný index]]. 
35. [[Sloupcové databáze|Sloupcové databáze]] - koncept, sloupcově orientovaný model, výhody a nevýhody. 
	- [[Cassandra|Cassandra]] - [[Cassandra#Architektura|architektura]], [[Cassandra#Distribuce dat|distribuce dat a replikace]], sekundární index. 
36. Dávkové zpracování dat - [[MapReduce|MapReduce]] (princip, fáze [[MapReduce#Mapovací funkce|mapování]] a [[MapReduce#Redukční funkce|redukování]]). 
	- [[Apache Hadoop|Apache Hadoop]] popis, důvod vzniku, ekosystém, komponenty a jejich význam (HDFS, YARN, MapReduce). 
37. [[Apache Spark|Apache Spark]] - popis a srovnání s [[Apache Hadoop|Apache Hadoop]], jednotlivé komponenty a jejich význam. Koncepty RDD a DataFrame - princip, popis a rozdíly. Transformace vs. akce. 
38. Proudové (streamové) zpracování dat - Spark Streaming a Structured Streaming - popis, rozdíly, výhody a nevýhody. Okna a práce s nimi. 