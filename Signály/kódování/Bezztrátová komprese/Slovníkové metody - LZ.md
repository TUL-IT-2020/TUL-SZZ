# Slovníkové metody - LZ
Statický slovník - moc nefunguje.
Dynamický slovník:
- LZ77
- LZ78
- LZW

## LZ 77
Dvě okna, průběžně se posouvají.
Větší okno, menší okno.
Úsek v malém okně nahradíme odkazem do většího okna, kde hledáme výskyty.

| Velké okno                  | Malé okno      |
| --------------------------- | -------------- |
| She sells sea shells on     | the sea shore. |
| S[he se]lls sea shells on | "he se"        |
| She sells se[a sh]ells on | "a sh"         |

## LZ 78, LZW
Autoři:
- L - Lempel
- Z - Ziv
- W - Welch

Slovník budován průběžně.
1. Do slovníku dáme znaky abecedy

Zpráva: AABBAABAB

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

Kódovaná zpráva: 1122362

Stačí přenést jen zdrojovou abecedy.
Slovník obvykle končí na 4096 pozicích ($2^{12}$).

## Příklady
- [[LZW příklad]]