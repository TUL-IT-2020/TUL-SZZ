# Relační model dat - RMD
Založen na pevném matematickém základu roku 1970 panem E. F. Coddem. 

*Entita* je objekt, o kterém budeme do databáze vkládat nějaká data, *atribut* je vlastnost objektu (entity) a relace je vztah mezi dvěma entitami.

## Základní rysy
- oddělení dat a jejich implementace
- symetrický přístup k datům - při manipulaci s daty se nezajímáme o přístupové mechanizmy k datům
- prostředky pro manipulaci s daty:
	- **relační kalkul**
	- **relační algebra** 

## Relační návrh databáze 
Vychází z [[RMD - Modelování relačního modelu pomocí UML digramu|konceptuálního schématu]] a vytvořené dokumentace. 
1. Přizpůsobit konceptuální schéma 
2. Transformovat na relační schéma 
3. Validovat relační schéma normalizací 
4. Validovat relační schéma vůči požadovaným transakcím 
5. Zkonzultovat navržený diagram se zákazníkem

## Základní pojmy
- **databázová relace** - množina (výsledek dotazu, tabulka, aj.); nesmí obsahovat duplicitní prvky
- **entita** - definovaná množina dat (např. tabulka)
	- **atribut** - An; jméno atributu
	- **doména atributu** - Dn; definiční množina hodnot atributu
		- rozsahy, kusovníky 
		- datový typ a délka atributu 
		- defaultní hodnota
- **schema relace** - je R(An:Dn); říká nám to, jaký je název relace, kolik má sloupců a jaké jsou jejich názvy a domény = definice databázové tabulky
- **atribut relace** - je dvojice An:Dn
- **n-tice** - jsou prvky relace
- **řád relace** - n z pojmu n-tice určuje řád relace
- **relační schema** - je dvojice (R,I), kde R je schema relace a I je množina integritních omezení

### Entita
E(A) – čti entita E má množinu atributů A. Často podstatné jméno v jednotném čísle. 
Příklad: STUDENT(rodne_cislo, jmeno, prijmeni, prumer)

Instance entity je konkrétní výskyt (prvek) entity a je jednoznačně odlišitelná.

### Atribut
Je vlastnost entity, která nás zajímá a jejíž hodnotu chceme mít v DB uloženou. Má datový typ a jeho hodnota může být proměnlivá (věk), nebo stálý (datum narození). Je vhodné volit spíš atributy stálé.

- atomický (jednoduchý) vs složený (např. adresa = psč, město, ulice) 
- jednohodnotový vs vícehodnotový (např. telefonní číslo) 
- odvozený (věk, celkový počet pracovníků, kauce = 3x měsíční renta)

### Vztah 
Je vazba, asociace mezi entitami. Příklad: Student se hlásí na školu.
stupeň vztahu = počet entit ve vztahu (binární, ternární, vazba sama na sebe (rekurzivní))
Instance vztahu, příklad: Alice se hlásí na TUL.

Vztahy realizujeme pomocí klíčů.

## Integrita databáze a integritní omezení
Integrita databáze znamená, že databáze vyhovuje zadaným pravidlům – integritním omezením. Tato integritní omezení jsou součástí definice databáze, a za jejich splnění zodpovídá SŘBD.

Mezi integritní omezení patří:
- **primární klíč** - množina atributů jednoznačně určující n-tici relace,
- **kandidáti primárního klíče** - obdoba primárního klíče, avšak kandidátů může být více,
- **klíčový atribut** - atribut, který je součástí některého klíče,
- **neklíčový atribut** - atribut, který není součástí žádného klíče,
- **referenční integrita** - popisuje vztahy mezi daty ve dvou relacích,
- **cizí klíč** - atribut, kterého se týká referenční integrita (foreign key).
- **kardinalita** - vlastnost binárních vztahů která určuje kolik instancí entit vstupuje do vztahu 
	- 1:1 
	- 1:N 
	- M:N
- **parcialita** - vyjadřuje, zda je účast ve vztahu povinná nebo volitelná,
	- totální (povinný) musí 
	- parciální (nepovinný) může
- Silná/slabá entita:
	- Silná entita – je identifikačně a existenčně nezávislá, 
	- Slabá entita – je identifikačně a existenčně závislá na jiné entitě.
- duplicitní prvek - relace nesmí obsahovat duplicitní prvky.

### Silná/slabá entita
Pokud máme slabou entitu, nelze její instance rozlišit pouze podle vlastních atributů. Identifikujeme jí tedy pomocí toho, že je v povinném tzv. identifikačním vztahu k jiné rodičovské entitě. Její primární klíč bude složený a bude obsahovat i primární klíč rodičovské entity. 
Příklad: kopie-kniha, sál-kino

### Klíče
X je klíč relace R pokud:
- všechny atributy R jsou funkčně závislé na X tj. v uzávěru Xᐩ jsou všechny atributy relace R
- neexistuje podmnožina X, na které jsou funkčně závislé všechny atributy R. (minimální)

V klíči musí být všechny atributy, které nejsou v žádný FZ. Klíčů může být víc.


#### Kandidátní klíč 
je atribut nebo kombinace atributů, které jednoznačně identifikují n-tice a žádný atribut v nich není nadbytečný. 

#### Primární klíč 
Je nejvhodnější kandidátní klíč (preferujeme číslo před textovým řetězcem), může být uměle vytvořený. Podtrháváme jej. Je to atribut nebo kombinace atributů, jejichž hodnoty jednoznačné odliší jednu instanci dané entity od druhé.

#### Cizí klíč 
Je atribut, který reprezentuje primární klíč jiné relace, reprezentuje vztah k jiné relaci.

### Zabezpečení integrity
Strategie když existuje dítě, kterého hodnota cizího klíče odkazuje na primární klíč, který má být změněn, nebo vymazán. 
1. NO ACTION – nemůžeš smazat, existují na něj odkazy 
2. CASCADE – vymaž i záznamy, které na něj odkazují 
3. SET NULL – vymaž a odkaz nastav na NULL 
4. SET DEFAULT – vymaž a odkaz nastav na defaultní hodnotu 
5. NO CHECK – bez kontroly

## Relační tabulka
Každá relační tabulka musí splňovat následující podmínky:
- sloupce mohou být v libovolném pořadí,
- řádky mohou být v libovolném pořadí,
- sloupce musí být homogenní = ve sloupci musí být údaje stejného typu,
- každému sloupci musí být přiřazeno jednoznačné jméno (tzv. atribut),
- v relační tabulce nesmí být dva zcela stejné řádky,
- dle relační teorie lze pomocí základních operací (sjednocení, kartézský součin, rozdíl, selekce, projekce, přejmenování) uskutečnit veškeré operace s daty.

## Základní operace
Dle relační teorie lze pomocí základních operací:
- sjednocení,
- kartézský součin,
- rozdíl,
- selekce,
- projekce,
- přejmenování

uskutečnit veškeré operace s daty. Příkladem použití může být [[Jazyk SQL|jazyk SQL]].

