# D-algoritmus
Hledáme jaké vstupy má mít obvod aby při dané poruše došlo ke změně výstupu. 

> [!note]
Formální tvoření citlivé cesty bez intuice.

1. Vytvoříme D-krychle obvodu.
2. Zvolíme si poruchu.
3. Vytvoříme primitivní D-krychle poruchy.
4. Propagace D na výstup (citlivá cesta)
5. Konzistence vektorů (zpětný průchod)
6. Pokračuji krokem 2 a zvolím si jinou poruchu.

## Singulární pokrytí
Zhuštěný tvar pravdivostní tabulky, v němž jsou sdruženy sousední vrcholy, které mají stejnou hodnotu výstupu (symbol X).
### g(AND)

| A   | B   | C   |
| --- | --- | --- |
| 0   | X   | 0   |
| X   | 0   | 0   |
| 1   | 1   | 1   |

### g(NAND)

| A   | B   | C   |
| --- | --- | --- |
| 0   | X   | 1   |
| X   | 0   | 1   |
| 1   | 1   | 0   |

### g(OR)

| A   | B   | C   |
| --- | --- | --- |
| 1   | X   | 1   |
| X   | 1   | 1   |
| 0   | 0   | 0   |

### g(NOR)

| A   | B   | C   |
| --- | --- | --- |
| 1   | X   | 0   |
| X   | 1   | 0   |
| 0   | 0   | 1   |
## D-krychle základních logických hradel
Formálně popisuje podmínky existence citlivé cesty. Vytvoříme ji jako průnik řádků (krychlí) singulárního pokrytí.

Pro průnik platí tato pravidla:
- $0 \cap 0 = 0$, $0\cap X = 0$, $X\cap 0 = 0$ 
- $1\cap 1 = 1$, $1\cap X = 1$, $X\cap 1 = 1$ 
- $X\cap X = X$
- $1 \cap 0 = D$
- $0 \cap 1 = D´$

D = 1-> 0
D'= 0 -> 1

### Přenosové D-krychle
Přenosová má D i na vstupu.

AND:

| A   | B   | C   |
| --- | --- | --- |
| D | 1 | D |
| 1 | D | D |

NAND:

| A   | B   | C   |
| --- | --- | --- |
| D |1 | D´ |
| 1 | D | D´ |

OR:

| A   | B   | C   |
| --- | --- | --- |
| D | 0 | D |
| 0 | D | D |

NOR:

| A   | B   | C   |
| --- | --- | --- |
| D | 0 | D´ |
| 0 | D | D´ |
