#příklad
# Huffmanovo kódování příklad
## Příklad komprese
Znakový řetězec: `ABRAKADABRA`
### Postup
1) četnosti A (5x – 0,46), R (2x – 0,18), B (2x – 0,18), K (1x – 0,09), D (1x – 0,09)
2) vytvoření tabulky dle četností
3) poslední dvě četnosti se sečtou a zařadí se do tabulky, sčítá se až do 1

| četnosti | bit | četnosti | bit | četnosti | bit | četnosti | bit |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| A 0,46 |  | A 0,46 |  | A 0,46 |  | KDBR 0,54 | 1 |
| R 0,18 |  | R 0,18 |  | KDB 0,36 | 1 | A 0,46 | 0 |
| B 0,18 |  | B 0,18 | 1 | R 0,18 | 0 |  |  |
| K 0,09 | 1 | KD 0,18 | 0 |  |  |  |  |
| D 0,09 | 0 |  |  |  |  |  |  |

4) Posledním dvěma slovům v každém sloupci tabulce přiřadíme 1 (vyšší četnost) a 0 (nižší četnost)
5) Výsledný kód znaku ==> posloupnost 0 a 1 dle toho jak se znak seskupoval s
dalšími znaky, např. pro znak K: (1) – KDBR, (1) KDB, (0) KD a (1) K. Výsledné
kódy A (0), R (10), B (111), K (1101), D (1100)
6) Výsledný řetězec pro ABRAKADABRA: 0 111 10 0 1101 0 1100 0 111 10 0, tj.:
01111001101011000111100

### Řešení
Výsledný řetězec po zakódování: `01111001101011000111100`
Kompresní poměr (pokud 1 znak = 8 bit.): 0,26 (26%)

## Příklad dekomprese
Dekóduje se podle slovníku.

## Příklad
Standardizovaná Huffmanova konstrukce. Určete střední délku kódového slova.
znaky: 0,2,4,6,8
p(x) = 0.2

### Postup
| Kód | Znak | četnosti | bit | četnosti | bit | četnosti | bit |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| 00 | 0 | 0.2 |  | 0 0.2 | 0 | 068 0.6 | 0 |
| 10 | 2 | 0.2 | 0 | 24 0.4 |  | 24 0.4 | 1 |
| 11 | 4 | 0.2 | 1 |  |  |  |  |
| 010 | 6 | 0.2 | 0 | 68 0.4 | 1 |  |  |
| 011 | 8 | 0.2 | 1 |  |  |  |  |

### Řešení
| Znak | Kód |
| ---- | ---- |
| 0 | 00 |
| 2 | 10 |
| 4 | 11 |
| 6 | 010 |
| 8 | 011 |
$\bar d = 0.2(3*2 + 2*3) = 2,4$

## Příklad

| Znak | a | b | c | d | e | f | g | h | i |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| $četnost*49$ | 7 | 3 | 6 | 2 | 9 | 2 | 6 | 6 | 8 |
### Postup
| Kód | Znak | $četnost*49$ | bit | četnosti | bit | četnosti | bit | četnosti | bit | četnosti | bit |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| 00 | e | 9 |  | e 9 |  | e 9 | 0 | egh 21 |  | egh 21 | 0 |
| 100 | i | 8 |  | i 8 |  | gh 12 | 1 |  |  | iacbdf 28 | 1 |
| 101 | a | 7 |  | a 7 |  | i 8 | 0 | ia 15 | 0 |  |  |
| 110 | c | 6 |  | c 6 |  | a 7 | 1 |  |  |  |  |
| 010 | g | 6 |  | g 6 | 0 | c 6 | 0 | cbdf 13 | 1 |  |  |
| 011 | h | 6 |  | h 6 | 1 |  |  |  |  |  |  |
| 1110 | b | 3 |  | b 3 | 0 | bdf 7 | 1 |  |  |  |  |
| 11110 | d | 2 | 0 | df 4 | 1 |  |  |  |  |  |  |
| 11111 | f | 2 | 1 |  |  |  |  |  |  |  |  |

Mno v sešitě nám to vyšlo jinak...

$\bar d = \frac{1}{49}(9*2+8*3+7*3+3*6*3+4*3+5*2*2)$
$\bar d = \frac{149}{49} \approx 3$


