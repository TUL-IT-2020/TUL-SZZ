# Průchod čtvercovou sítí

## Příklad
Kolika různými způsoby se lze dostat pomocí kroků typu:
- 0. $[x,y] -> [x+1,y]$
- 1. $[x,y] -> [x,y+1]$

Z bodu $[-2,-1]$ do bodu $[8,8]$, jestliže musíme projít bodem $[3,5]$?

### Postup
Rozložíme cestu na dvě části:
- $[-2,-1] -> [3,5]$
- $[3,5] -> [8,8]$

Posun cesty do bodu $[0,0]$:
- $[0,0] -> [5,6]$
- $[5,6] -> [10,9]$

### Řešení
$$
P(5,6) * P(5,3)
$$

## Příklad
Z bodu $[-2,1]$ do bodu $[6,9]$, tak aby v každém okamžiku platilo $y \leq x+3$.

### Postup
Graficky:
Přímka kterou nesmíme překročit, omezená na x od -1 do 6, $y = x+3$

Posunutí cesty do bodu $[0,0]$:
- $[0,0] -> [8,8]$

Z omezující přímky se stane $y = x$, tedy diagonála.

### Řešení
$$
C_8 = 1/9 C_15^8
$$