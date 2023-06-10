# CAP teorém
3 základní vlastnosti distribuovaných systémů. Systém může splňovat nejvýše 2 z nich najednou. 
Slouží návrhářům k ujasnění priorit.

![[CAP teorém.PNG]]
## CAP význam zkratek
Při návrhu distribuované aplikace je nutné brát v potaz následující požadavky:
### Consistency
Konzistence, pro každý požadavek je vrácen správný výsledek, data musí zůstat konzistentní i po provedení operace. 
Distribuované úložiště: každý uzel vrací aktuální a stejná data. 
Výpočet: výsledky od jednotlivých uzlů se neliší.

### Availability
Dostupnost, systém musí být stále dostupný, tzn. že každý dotaz dostane odpověď, zda byl proveden úspěšně či selhal.

### Partition tolerance
Tolerance výpadku, partitioning ve smyslu výpadku či rozdělení sítě. Určuje chování podpůrného systému, na kterém služba běží. Systém musí být schopen stále komunikovat, i když je komunikace mezi severy nespolehlivá.

![CAP distribuovaná aplikace](14_cap1.png)

## Výběr priorit
Teoreticky není možné splnit všechny tři požadavky najednou. CAP říká, že základní požadavky na distribuované systémy musí splňovat dva ze tří požadavků. Různé NoSQL databáze tedy podporují různé kombinace C, A, P. 
Reálně by každý systém měl zajišťovat partition tolerance, proto jde o tradeoff mezi A, C.

![CAP distribuovaná aplikace](14_cap2.png)

### C + A  ([[RMD - Relační model dat|relační DB]])
Výpadek části sítě je problém. Než aby systém vrátil nekonzistentní výsledky, neodpoví vůbec. Data jsou konzistentní mezi všemi uzly, pokud jsou všechny uzly online. Můžeme číst/zapisovat z kteréhokoli uzlu a být si zároveň jisti, že data jsou stejná. 

### C + P ([[MongoDB|Mongo]])
Data jsou konzistentní mezi všemi uzly a zachovávají partition tolerance (zamezují desychroznizaci) tím, že pokud je uzel offline data jsou nedostupná. Pokud systém nedokáže vrátit aktuální data, vrátí chybu.

### A + P ([[Cassandra|Cassandra]])
Tolerantní vůči výpadku části služby. Systém je dostupný díky replikaci, k synchronizaci dojde hned jak bude partition znovu dostupná. Nicméně není garantováno, že všechny uzly budou mít stejná data. Neexistuje záruka, že data jsou aktuální. 

## Segmentovaná konzistence a dostupnost
Každá komponenta systému splňuje část CAP.
Rozdělení podle dat:
- Jiná data mohou vyžadovat jinou úroveň dostupnosti
- Filesystémy
Rozdělení podle operací:
- Operace pro zápis mohou mít jiné požadavky na konzistenci a dostupnost než operace pro čtení
- DB systémy


