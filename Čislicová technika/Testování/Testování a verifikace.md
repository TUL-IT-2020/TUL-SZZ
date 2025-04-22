# Testování a verifikace
[[Defekty a poruchy]]

![[s_AMD_80386DX_die.jpg]]

Testujeme i na neočekávané vstupy

Verifikace -> ověření návrhu pracuje s modelem (umí Pentium počítat?)
Testování -> ověření fyzické součástky (vyrobili jsme to dobře?)

Formální verifikace -> porovnáváme zda dva různého modely téhož mají stejnou funkci.

Diagnostika = lokalizace
Testování = detekce

## Testování 

> [!info] "Testování"
> Funguje to vs nefunguje to.

> [!warning] Očekáváme že v jeden čas existuje právě jedna porucha

### Terminologie:
Funkční -> testuji všechny vykonávané funkce (známe chování obvodu, popis jeho funkcí)
Strukturní -> testujeme strukturu, menší počet vektorů (známe vnitřní strukturu)

**Test vector** -> digitální vzorky které přivádíme na vstupy
**Test pattern** -> testovac vekor + jeho odezva
**Test set** -> množina vstupů a výstupů (n x vector)
**Test sequnce** -> testovací vzory v časové posloupnosti

- Fault simulation - chování v případě poruchy
#### Test
Test je množina kroků ověřující funkčnost.
Krok testů (dvojice vstup výstup - test vector).

Strukturní:
- náhodné ->n testovacích vektorů
- triviální -> pravdivostní tabulka (velká)
- deterministické -> ATPG, zcitlivění cesty

- úplný test -> pokrývá všechny poruchy (otestuje celý hw)
- minimální test -> čas jsou peníze, tak ať to netrvá dlouho

### Defekt level
> [!tip] Yield
$$
Yield = \frac{Good}{All} 
$$
$$
Y = (1-P)^n
$$

> [!example]
>- P - probability of a defect
>- n -  number of defects
>- T -  test coverage (test quality)

> [!tip] Defekt level
$$
DL = 1 - Y^{(1-T)}
$$

> [!tip] Pokrytí poruch
$$
F = \frac{foults \; covered \; by \; test}{total \; number \;of\; faults}
$$
### Návrh testů:
- Chování
- struktura
- fyzikální jevy

|             | Domain                 |                |                |
| ----------- | ---------------------- | -------------- | -------------- |
| Level       | **Behavioral**         | **Structural** | **Physical**   |
| **System**  | System Specifications  | Blocks         | Chip           |
| **RTL**     | RTL Specifications     | Registers      | Macro Cells    |
| **Logic**   | Boolean Functions      | Logic Gates    | Standard Cells |
| **Circuit** | Differential Equations | Transistors    | Masks          |

> [!example] Testování na různé úrovni:
>- program,
>- ISA,
>- registry,
>- hradla,
>- tranzistory.
### Design pro snadnou testovatelnost
![[Design pro snadnou testovatelnost]]

### Redundance
Všechny redundantní obvody musí mít možnost otestování!
Pokud sami jednu chybu opravím, tak základním testem nelze odhalit!

[[TMR]] - triple module redundanci

Online vs Offline
Pokud máme redundantní návrh, tak můžeme za běhu validovat zařízení že pracuje správně.  
## Metody testování
### Intuitivní zcitlivění cesty
![[Intuitivní zcitlivění cesty]]

### D-algoritmus
![[D-algoritmus]]

### Boolovská diference
![[Boolovská diference]]

### IDDQ
![[IDDQ]]

## Tabulky úplných testů

Jak otestovat zřetězené zapojení obvodů?

- **Stimul** nastavuje testovací vektory na dalším bloku.
- **Transformace** testovacích vektorů.
- **Citlivá cesta** vedoucí ven z obvodu.

> [!warning] Problém:
> - těžko minimalizovatelné testy, duplicitní nastavovací vektory.
> - nemusí být možné mezi bloky nastavit libovolný vektor hodnot.
> - Stavové automaty zvyšují náročnost testovaní o řád.

## Sekvenční obvody
![[Testování sekvenčních obvodů]]