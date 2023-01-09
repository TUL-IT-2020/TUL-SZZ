# Tematické okruhy ke státní závěrečné zkoušce na FM TUL

## Určeno pro studenty bakalářského programu Informační technologie

### Specializace: Inteligentní systémy

**Matematika:**

1. Derivace, diferenciál a integrál (definice, výpočty, praktický význam).
2. Soustava lineárních rovnic a metody jejich řešení.
3. Maticová algebra, typy matic, inverzní matice, determinant.
4. Vlastní čísla a vlastní vektory matic. Způsob výpočtu a praktická interpretace.
5. Soustavy lineárních rovnic a metody jejich řešení.
6. Pojem pravděpodobnost, náhodný jev. Podmíněná pravděpodobnost, nezávislost. Náhodná
veličina – diskrétní, spojitá a jejich použití. Střední hodnota, kvantily, rozptyl.

**Signály, zpracování informace:**  

7. Signály a systémy. LTI systémy. Přenosová funkce, impulsní odezva. Konvoluce u číslicových
signálů.  
8. Fourierovy řady. Diskrétní Fourierova transformace, její použití a interpretace. Spektrum  
signálu, FFT. Číslicové filtry FIR a IIR. Filtrace v čase nebo prostoru.  
9. Vzorkování, kvantování. Vzorkovací teorém. Aliasing.

**Strojové učení a vytěžování dat**

10. Základní typy úloh strojového učení a rozdělení dat. Základy klasifikace, vyhodnocování
výsledků, matice záměn.
11. Regrese, analytické řešení metodou nejmenších čtverců, numerické řešení metodou největšího
spádu.
12. Binární lineární klasifikace a logistická regrese, učení modelu logistické regrese.
13. Lineární klasifikace do více tříd, způsoby učení, softmax.
14. Nelineární klasifikace a neuronové sítě typu vícevrstvý perceptron, učení neuronových sítí -
algoritmus zpětné propagace.
15. Konvoluční neuronové sítě a jejich aplikace. Rekurentní neuronové sítě a jejich aplikace,
modely typu [[LSTM|LSTM]] a GRU.
16. Attention mechanismus v umělých neuronových sítích a jeho aplikace.
17. [[Vector Space Model|Vektorová reprezentace slov]] a její [[Word2Vec retrieval model|aplikace]], [[Word2Vec|Word2Vec]] a [[GloVe|GloVe]].
18. Metody učení bez učitele, shlukování - algoritmus [[K-means|K-means]] a [[LBG|LGB]], [[Hierarchické shlukování|hierarchické shlukování]].

**Algoritmy a programování:**

19. Číselné soustavy a převody mezi nimi. Způsoby kódování čísel s pevnou a s pohyblivou
řádovou tečkou. Kódování záporných čísel.
20. Jazyk C: základní datové typy a strukturovaný datový typ. Pole a ukazatele, dynamická alokace
paměti.
21. Algoritmy pro vyhledávání a řazení, složitost algoritmů.
22. Rekurze a její použití. Rekurzivní a nerekurzivní realizace vybraných algoritmů. Využití
zásobníku programu.
23. Členění programu v jazyce vyšší úrovně. Metody, funkce, procedury, makra. Parametry metod,
procedur a funkcí a způsoby jejich předávání. Globální a lokální proměnné.
24. Objektově orientované programování, význam a základní principy: zapouzdření, dědičnost a
polymorfismus, správa přístupu.. Abstraktní třídy a rozhraní. Genericita a její využití.
25. Operační systém, vysvětlení pojmu, typy, poskytované funkce. Správa procesů v operačním
systému, vztah programu a procesu, životní cyklus procesu.

**Počítačové sítě a Internet:**

26. Principy vrstvené architektury počítačových sítí, referenční model OSI. Charakteristika
lokálních počítačových sítí. Technologie Ethernet, její principy a vývoj, algoritmus CSMA/CD.
Bezdrátové lokální sítě standardu IEEE 802.11.
27. Základní principy činnosti protokolů sítě Internet – IP, TCP, UDP. Domain Name System, jeho
role a činnost, DNS servery, postup řešení dotazu, reverzní DNS.

**Databázové systémy a technologie pro BigData:**

28. Architektura relačních databázových systémů, datový model, konceptuální modelování.
29. Relační model, základní konstrukty, realizace vztahů v relačním modelu, integritní omezení.
Normalizace, normální formy, funkční závislosti, aktualizační anomálie.
30. [[Jazyk SQL|Jazyk SQL]] - selekce, projekce, agregační funkce, [[Množinové operace|množinové operace]], typy spojení, vnořené
dotazy, spouště a uložené procedury.
31. Transakce – koncept a vlastnosti transakcí (ACID).
32. BigData - definice, dělení podle struktury a původu, charakteristika, aplikace. Analýza velkých
dat - jednotlivé kroky, typy, výhody a výzvy.
33. NoSQL databáze - koncept, vlastnosti, dělení, srovnání s relačními databázemi. Pojmy: volné
schéma, CAP teorém, indexování, agregace, replikace, škálování, sharding.
34. Dokumentové databáze - koncept, srovnání s key-value úložišti, pojem dokument, výhody a
nevýhody. MongoDB - charakteristika a architektura.
35. Databáze pro prohledávání a analýzu textu - princip, vlastnosti. Elasticsearch - architektura,
prohledávání vs. analýza, invertovaný index.
36. Sloupcové databáze - koncept, sloupcově orientovaný model, výhody a nevýhody. Cassandra -
architektura, distribuce dat a replikace, sekundární index.
37. Dávkové zpracování dat – MapReduce (princip, fáze mapování a redukování). Apache Hadoop
	- popis, důvod vzniku, ekosystém, komponenty a jejich význam (HDFS, YARN, MapReduce).
38. Apache Spark – popis a srovnání s Apache Hadoop, jednotlivé komponenty a jejich význam.
Koncepty RDD a DataFrame - princip, popis a rozdíly. Transformace vs. akce.
39. Proudové (streamové) zpracování dat - Spark Streaming a Structured Streaming - popis,
rozdíly, výhody a nevýhody. Okna a práce s nimi.