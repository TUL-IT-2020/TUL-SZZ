#MVD 
# MapReduce
Model pro paralelní zpracování velkého množství dat. Minimalizuje potřebné úsilí programátora pro jednoduché úlohy paralelního zpracování dat. Programovací model pro distribuované paralelní výpočty. Původně od Google. Tvoří jej master-slave architektura.

Základní myšlenka: *výpočet k datům, ne data k výpočtu*.
Dvě fáze: *mapování a redukce*.

Výhody: 
- Skrývá před programátorem většinu low-level detailů (síť, úložiště),
- Odolnost proti chybám, 
- Automatické vyvažování zátěže,
- Levnější na přesuny po síti, 
- Méně náchylné na chyby při přesunu, 
- Lepší škálovatelnost.

## Mapovací funkce 
Vstupem je seznam prvků, na které je aplikována transformace. Bezstavová [[funkcionální programování|funkce]] (například: převod stringů do upper case)

## Redukční funkce 
Agreguje seznam hodnot, který jí je poskytnut, do menšího množství (například: jednoduchý součet). 

## Postup výpočtu:
1. **Rozdělení vstupu** - na jednotlivé části podle počtu mapperů,
2. **Mapování** - tvorba dat ve formátu klíč, hodnota,  
3. **Shuffle & sort** - třídění dat podle klíče a rozesílání reducerům, 
4. **Redukce** - agregace párů se stejným klíčem.

## Využití
- Analytické úlohy
- Klasifikace
- Data mining
- Indexace a vyhledávání
- Konkrétní příklady:
	- Google – generování Google indexu
	- [[Apache Hadoop|Apache Hadoop]] – spojení HDFS
