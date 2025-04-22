# Obvody bezpečné proti poruchám

![[TMR]]

Dopad radiace na paměť
SEUs - Single event upsets


> [!tip] Obvody bezpečné proti poruchám
Obvody je bezpečný pro jedno poruchy, jestliže pro každý vstupní vektor a poruchu platí že odezva je:
>- správná,
>- chybový stav.

Dostaneme stav chybu, nebo správný výsledek.
## Zdvojení logiky
### Dvakrát stejná funkce
```mermaid
flowchart LR
    F1(F)
    F2(F)
    A((A)) -->  F1
    B((B)) -->  F1
    A --> F2
    B --> F2
    F1 --> Y1((Y1))
    F1 --> Y2((Y2))
    F1 --> XOR_1
    F2 --> XOR_1

    F1 --> XOR_2
    F2 --> XOR_2
    XOR_1--> OR
    XOR_2--> OR
    OR --> E((ERR))
```

### Funkce a její opak
F -> F-1
```mermaid
flowchart LR
    F1(F)
    F2(F-1)
    A((A)) -->  F1
    B((B)) -->  F1

    F1 --> F2
    F1 --> F2
    A --> XOR_1

    F2 --> XOR_1
    F2 --> XOR_2
    B --> XOR_2

    XOR_1--> OR
    XOR_2--> OR
    OR --> E((ERR))
    F1 --> Y1((Y1))
    F1 --> Y2((Y2))
```
Jestliže obvod realizuje prosté zobrazení, je možné navrhnout obvod realizující inversní funkci.
Pravděpodobnost současného výskytu poruch v obou blocích je nízká.
### Dvoudrátová logika
Proto z 74xx má negované výstupy.

Vyhodnocujeme najednou přímou a negovanou větev.

Výhodné pro průběžnou kontrolu správnosti funkce i sekvenčních obvodů. Transitivita chyby v libovolně dlouhém řetězci logických členů. S prodlužováním řetězce ale vzrůstá pravděpodobnost výskytu vícenásobné chyby.

## Hlídací/záložní procesor
