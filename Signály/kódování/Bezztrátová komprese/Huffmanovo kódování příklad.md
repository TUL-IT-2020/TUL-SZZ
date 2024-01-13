#příklad
# Huffmanovo kódování příklad
## Příklad komprese
Znakový řetězec: `ABRAKADABRA`
### Postup
1) četnosti A (5x – 0,46), R (2x – 0,18), B (2x – 0,18), K (1x – 0,09), D (1x – 0,09)
2) vytvoření tabulky dle četností
3) poslední dvě četnosti se sečtou a zařadí se do tabulky, sčítá se až do 1

|četnosti|bit|četnosti|bit|četnosti|bit|četnosti|bit|
|---|---|---|---|---|---|---|---|
| A 0,46 || A 0,46 ||A 0,46||KDBR 0,54|1|
|R 0,18||R 0,18||KDB 0,36 |1| A 0,46 |0|
|B 0,18||B 0,18|1|R 0,18|0|
|K 0,09|1|KD 0,18|0|
|D 0,09|0|

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
