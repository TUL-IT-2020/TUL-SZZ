# BIST
BIST - Built-In Self Test
MBIST - Memory BIST

## Testování je pomalé
> [!question] Testování je pomalé co s tím?

Přesunutí TPG do integrovaného obvodu

Analýza příznaků
- vytvoření kratšího vektoru (komprese), která nese informaci o stavu, ale je rychlejší ji odeslat do (vnějšího) testeru

[[Design pro snadnou testovatelnost]]
## Typy testovacích vzorů:
> [!example] Typy testů:
>- **Exhaustive** - vyčerpávající tedy všechny možné kombinace
>- **Pseudoexhaustive** - "všechny" které dávají smysl vůči struktuře obvodu.
>- **Deterministický** - generátor úplného testu
>- **Weighted random** - `1` a `0` mají na svých pozicích různé pravděpodobnosti výskytu. 

Nízký přenos dat.

Test-per-clock (TPC) - rychlejší, těžké zachytit všechny signály
Test-per-Scan (TPS) - test po výčtu posuvného registru

LSFR
Stav samé nuly je konečný.

CA - buněčné automaty
Posloupnot T buněk s zpětnou vazbou. Generuje "náhodnější" vzorky než LSFR.
Convays game of life

Mixed mode - co jde vygenerujeme random, přidáme pár vzorků pro úplné pokrytí.