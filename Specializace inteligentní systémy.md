# Tematické okruhy ke státní závěrečné zkoušce na FM TUL

## Určeno pro studenty bakalářského programu Informační technologie

### Specializace: Inteligentní systémy

**Matematika:**

1. Derivace, diferenciál a integrál (definice, výpočty, praktický význam).
2. Soustava lineárních rovnic a metody jejich řešení.
3. Maticová algebra, typy matic, inverzní matice, determinant.
4. Vlastní čísla a vlastní vektory matic. Způsob výpočtu a praktická interpretace.
5. Pojem [[pravděpodobnost|pravděpodobnost]], [[náhodný jev|náhodný jev]]. [[Podmíněná pravděpodobnost|Podmíněná pravděpodobnost]], [[Statistická závislost a nezávislost|nezávislost]]. [[Náhodná veličina|Náhodná veličina]] – [[Diskrétní náhodné veličiny|diskrétní]], [[Hustota pravděpodobnosti|spojitá]] a jejich použití. [[Střední hodnota a rozptyl#STŘEDNÍ HODNOTA|Střední hodnota]], [[kvantil|kvantily]], [[Střední hodnota a rozptyl#Rozptyl|rozptyl]].

**Signály, zpracování informace:**  

6. Signály a systémy. LTI systémy. Přenosová funkce, impulsní odezva. Konvoluce u číslicových signálů.  
7. Fourierovy řady. Diskrétní Fourierova transformace, její použití a interpretace. Spektrum signálu, FFT. Číslicové filtry FIR a IIR. Filtrace v čase nebo prostoru.  
8. Vzorkování, kvantování. Vzorkovací teorém. Aliasing.

**Strojové učení a vytěžování dat**

9. Základní typy úloh strojového učení a rozdělení dat. Základy klasifikace, vyhodnocování výsledků, matice záměn.
10. Regrese, analytické řešení metodou nejmenších čtverců, numerické řešení metodou největšího spádu.
11. Binární lineární klasifikace a logistická regrese, učení modelu logistické regrese.
12. Lineární klasifikace do více tříd, způsoby učení, softmax.
13. Nelineární klasifikace a neuronové sítě typu vícevrstvý perceptron, učení neuronových sítí - algoritmus zpětné propagace.
14. Konvoluční neuronové sítě a jejich aplikace. Rekurentní neuronové sítě a jejich aplikace, modely typu [[LSTM|LSTM]] a GRU.
15. Attention mechanismus v umělých neuronových sítích a jeho aplikace.
16. [[Vector Space Model|Vektorová reprezentace slov]] a její [[Word2Vec retrieval model|aplikace]], [[Word2Vec|Word2Vec]] a [[GloVe|GloVe]].
17. Metody učení bez učitele, shlukování - algoritmus [[K-means|K-means]] a [[LBG|LGB]], [[Hierarchické shlukování|hierarchické shlukování]].

**Algoritmy a programování:**

18. Číselné soustavy a převody mezi nimi. Způsoby kódování čísel s pevnou a s pohyblivou řádovou tečkou. Kódování záporných čísel.
19. Jazyk [[C|C]]. [[C#Základní datové typy|Základní datové typy]] a [[C#Strukturovaný datový typ|strukturovaný datový typ]]. [[C#pole|Pole]] a [[C#Ukazatele (pointery)|ukazatele]], [[C#dynamická alokace pole|dynamická alokace]] [[Rozdělení paměti|paměti]].
20. Algoritmy pro vyhledávání a řazení, složitost algoritmů.
21. [[C#Rekurzivní funkce|Rekurze]] a její použití. Rekurzivní a nerekurzivní realizace [[Rekurze|vybraných algoritmů]]. Využití [[Rozdělení paměti#Zásobník|zásobníku programu]].
22. Členění programu v jazyce vyšší úrovně. Metody, [[C#Funkce|funkce]], procedury, [[C#Makra|makra]]. Parametry metod, procedur a funkcí a způsoby jejich předávání. Globální a lokální proměnné.
23. [[OOP|Objektově orientované programování]], význam a základní principy: zapouzdření, [[OOP#Dědičnost|dědičnost]] a polymorfismus, správa přístupu... [[OOP#Abstraktní třída|Abstraktní třídy]] a [[OOP#Rozhraní (inteface)|rozhraní]]. Genericita a její využití.
24. Operační systém, vysvětlení pojmu, typy, poskytované funkce. Správa procesů v operačním systému, vztah programu a procesu, životní cyklus procesu.

**Počítačové sítě a Internet:**
 
25. Principy vrstvené architektury počítačových sítí, referenční model OSI. 
	- Charakteristika lokálních počítačových sítí. Technologie Ethernet, její principy a vývoj, algoritmus CSMA/CD. 
	- Bezdrátové lokální sítě standardu IEEE 802.11.
26. Základní principy činnosti protokolů sítě Internet - IP, TCP, UDP. Domain Name System, jeho role a činnost, DNS servery, postup řešení dotazu, reverzní DNS.

**Databázové systémy a technologie pro BigData:**

27. Architektura relačních [[Databazove_systemy#Databázové systémy|databázových systémů]], [[Databazove_systemy#Konceptuální model|datový model]], [[RMD - Modelování relačního modelu pomocí UML digramu|konceptuální modelování]].
28. [[RMD - Relační model dat|Relační model]], [[RMD - Relační model dat#Základní pojmy|základní konstrukty]], [[RMD - Relační model dat#Vztah|realizace vztahů v relačním modelu]], [[RMD - Relační model dat#Integrita databáze a integritní omezení|integritní omezení]]. 
	- [[Mormalizace_BDS|Normalizace]], [[RMD - Normalizace|normální formy]], [[RMD - Funkční závislosti|funkční závislosti]], [[RMD - Návrhové anomálie|aktualizační anomálie]].
29. [[Jazyk SQL|Jazyk SQL]] - [[Jazyk SQL#DML / [SELECT](https //cs.wikipedia.org/wiki/SELECT)|selekce]], projekce, agregační funkce, [[SQL - Množinové operace|množinové operace]], [[SQL - Spojení tabulek|typy spojení]], vnořené dotazy, [[Uložené procedury a spouště (od SQL3)|spouště a uložené procedury]].
30. [[SQL - Transakce|Transakce]] - koncept a vlastnosti transakcí ([[SQL - ACID|ACID]]).
31. [[BigData|BigData]] - definice, dělení podle [[BigData#Struktura Dat|struktury]] a [[BigData#Odkud Big Data pochází?|původu]], [[BigData#Charakteristiky Big Data|charakteristika]], [[BigData#Aplikace Big Data|aplikace]]. 
	- [[BigData#Analýza velkých dat|Analýza velkých dat]] - jednotlivé kroky, typy, výhody a výzvy.
32. [[NoSQL databáze|NoSQL databáze]] - koncept, vlastnosti, dělení, srovnání s relačními databázemi. Pojmy: volné schéma, [[CAP teorém|CAP teorém]], indexování, agregace, replikace, škálování, sharding.
33. Dokumentové databáze - koncept, srovnání s key-value úložišti, pojem dokument, výhody a nevýhody. 
	- [[MongoDB|MongoDB]] - charakteristika a architektura.
34. Databáze pro prohledávání a analýzu textu - princip, vlastnosti. 
	- [[Elasticsearch|Elasticsearch]] - [[Elasticsearch#Architektura|architektura]], prohledávání vs. analýza, invertovaný index.
35. Sloupcové databáze - koncept, sloupcově orientovaný model, výhody a nevýhody. 
	- [[Cassandra|Cassandra]] - [[Cassandra#Architektura|architektura]], [[Cassandra#Distribuce dat|distribuce dat a replikace]], sekundární index.
36. Dávkové zpracování dat - [[MapReduce|MapReduce]] (princip, fáze [[MapReduce#Mapovací funkce|mapování]] a [[MapReduce#Redukční funkce|redukování]]). 
	- [[Apache Hadoop|Apache Hadoop]] popis, důvod vzniku, ekosystém, komponenty a jejich význam (HDFS, YARN, MapReduce).
37. [[Apache Spark|Apache Spark]] - popis a srovnání s [[Apache Hadoop|Apache Hadoop]], jednotlivé komponenty a jejich význam. Koncepty RDD a DataFrame - princip, popis a rozdíly. Transformace vs. akce.
38. Proudové (streamové) zpracování dat - Spark Streaming a Structured Streaming - popis, rozdíly, výhody a nevýhody. Okna a práce s nimi.