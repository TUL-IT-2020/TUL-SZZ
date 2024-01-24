# LZW (Lempel-Ziv-Welchův algoritmus)
Kompresní/dekompresní metoda, využití – přenos dat, GIF, TIFF, postscript
(+) rychlá metoda
(-) horší kompresní poměr (cca o 30% horší než nejlepší met.)

Autoři:
- L - Lempel
- Z - Ziv
- W - Welch

Slovník – ukládají se opakující se znaky. Slovník budován průběžně.
Pokud se vyskytne několik stejných posloupností znaků – nahrazení stejným
číslem
Slovník se neukládá, ale je znovu vytvořen ze zakódovaného souboru. Stačí přenést jen zdrojovou abecedy.

Slovník obvykle končí na 4096 pozicích ($2^{12}$).
## Příklad
Aplikujte algoritmus LZW na zprávu nad abecedou A,B. Zpráva je AABBAABAB.

### Postup
1. Do slovníku dáme znaky abecedy

| Slovník | kód |
| ------- | --- |
| A       | 1   |
| B       | 2   |
| AA      | 3   |
| AB      | 4   |
| BB      | 5   |
| BA      | 6   |
| AAB     | 7   |
| BAB     | 8    |
### Řešení
Kódovaná zpráva: 1122362
### Zdroje:
- [Jan Outrata, LZW](https://phoenix.inf.upol.cz/~outrata/download/programs/lzw.txt)
- [Wiki, LZW](https://cs.wikipedia.org/wiki/LZW)
## Příklady
- [[LZW příklad]]