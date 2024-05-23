#příklad
# MFT
## Příklad
Zakódujte ANANAS.
### Postup

| Znak | kód | změna abecedy |
|---|---|---|
|A | 1 | (poté: ABCDEFGHIJKLMNO...) |
|N | 14| (poté: NABCDEFGHIJKLMO...) |
|A|2| (poté: ANBCDEFGHIJKLMO…) |
|N|2| (poté: NABCDEFGHIJKLMO...) |
|A|2| (poté: ANBCDEFGHIJKLMO...) |
|S | 19 | (poté: SANBCDEFGHIJKLMO...) |

ANANAS – ASCII

| Znak | kód | změna abecedy |
|---|---|---|
|A | 65 | (poté A = 0)
|N | 78 |(poté N = 0, A = 1)
|A | 1 |(poté A = 0, N = 1)
|N | 1 |(poté N = 0, A = 1)
|A | 1 |(poté A = 0, N = 1)
|S |83 | (poté S = 0, A = 1…)
### Řešení

ANANAS bude zakódován jako $1, 14, 2, 2, 2, 19$.