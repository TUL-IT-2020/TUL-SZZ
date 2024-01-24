#SQL
# Návrhové anomálie
**Aktualizacní anomálie (Codd):**

*Aktualizační anomálie je nechtěný vedlejší efekt operace nad databází, při kterém dojde ke ztrátě nebo nekonzistenci dat.*

Relace: *PROGRAM_KINA(PK: JMENO_KINA, PK: JMENO_FILMU, ADRESA, DATUM, CAS)*

## Aktualizační anomálie:
- INSERT (chceme-li přidat nové kino s adresou, lze to jen když se tam hraje nejaký film)
- UPDATE (zmení-li se adresa kina, je nutné ji měnit vícekrát)
- DELETE (nehraje-li kino zrovna nic, ztrácíme jeho adresu)

## Podrobněji:
![[RMD - tabulky studentů.PNG]]

**Redundance dat** - uložené stejné data na více místech.

**Aktualizační anomálie** (pro operace, které mění obsah):

INSERT anomálie - při vložení nového záznamu (n-tice) musíme upravovat všechny výskyty a znát i všechny další atributy, u každého nového studenta musím vložit i adresu univerzity, kde se hlásí. Když to popletu, v DB budou dvě různé adresy pro jednu univerzitu. => nekonzistence dat. Když přidáme novou univerzitu, museli by jsme ostatní údaje vyplnit NULL.

DELETE anomálie - při vymazání může dojít ke ztrátě dat, když chci vymazat záznamy o Bobovi, vymažu i informaci, že TUL sídlí na Hálkovej 6. 

UPDATE anomálie - při změně musíme upravovat všechny výskyty, když chceme změnit příjmení studenta, musíme to změnit ve všech řádcích, kde se daný student vyskytuje. Když to popletu, v DB budou dva různí studenti se stejným rodným číslem. => nekonzistence dat.