# Relační model dat - RMD
Založen na pevném matematickém základu roku 1970 panem E. F. Coddem. 

## Základní rysy
- oddělení dat a jejich implementace
- symetrický přístup k datům - při manipulaci s daty se nezajímáme o přístupové mechanizmy k datům
- prostředky pro manipulaci s daty:
 - **relační kalkul**
 - **relační algebra** 

## Základní pojmy
- **databázová relace** - množina (výsledek dotazu, tabulka, aj.); nesmí obsahovat duplicitní prvky
- **entita** - definovaná množina dat (např. tabulka)
- **atribut** - An; jméno atributu
- **doména atributu** - Dn; definiční množina hodnot atributu
- **schema relace** - je R(An:Dn); říká nám to, jaký je název relace, kolik má sloupců a jaké jsou jejich názvy a domény = definice databázové tabulky
- **atribut relace** - je dvojice An:Dn
- **n-tice** - jsou prvky relace
- **řád relace** - n z pojmu n-tice určuje řád relace
- **relační schema** - je dvojice (R,I), kde R je schema relace a I je množina integritních omezení

## Integrita databáze a integritní omezení
Integrita databáze znamená, že databáze vyhovuje zadaným pravidlům – integritním omezením. Tato integritní omezení jsou součástí definice databáze, a za jejich splnění zodpovídá SŘBD.

Mezi integritní omezení patří:
- **primární klíč** - množina atributů jednoznačně určující n-tici relace,
- **kandidáti primárního klíče** - obdoba primárního klíče, avšak kandidátů může být více,
- **klíčový atribut** - atribut, který je součástí některého klíče,
- **neklíčový atribut** - atribut, který není součástí žádného klíče,
- **referenční integrita** - popisuje vztahy mezi daty ve dvou relacích,
- **cizí klíč** - atribut, kterého se týká referenční integrita (foreign key).
- **kardinalita** - vlastnost binárních vztahů která určuje kolik instancí entit vstupuje do vztahu (např. 1:1, 1:N, M:N),
- **parcialita** - vyjadřuje, zda je účast ve vztahu povinná nebo volitelná,
- silné entitní typy - součástí klíče jsou atributy pouze z dané entity (nikoli z jiných)
- slabé entitní typy - součástí klíče je atribut z jiné entity,
- duplicitní prvek - relace nesmí obsahovat duplicitní prvky.

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