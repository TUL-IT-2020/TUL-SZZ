# Grayovy kódy
Binární reprezentace čísel $<0, 2^n-1>$
Sousední čísla se liší právě v jednom bitu. 

| d   | GK  | GK  |
| --- | --- | --- |
| 0   | 000 | 00  |
| 1   | 001 | 01  |
| 2   | 011 | 11  |
| 3   | 010 | 10  |
| 4   | 110 |     |
| 5   | 111 |     |
| 6   | 101 |     |
| 7   | 100 |     |

![[gray_code.png]]

Rekurzivní konstrukce GK délky n z GK délky n-1

| GK n-1 | GK  |
| ------ | --- |
| 00     | 000 |
| 01     | 001 |
| 11     | 011 |
| 10     | 010 |
| ...       | ...    |
| 10     | 110 |
| 11     | 111 |
| 01     | 101 |
| 00     | 100 |

Přímá konstrukce
Vezmeme "normální binnární reperzentaci"
Př: 6 -> 110

1) Nejvyšší bit se nezmění
2) Změní se bity, před kterými je jednička

6 = 110 -> 101
2 = 010 -> 011


## Použití
- Rotační čidla 
- přepínače
- genetické algoritmy
