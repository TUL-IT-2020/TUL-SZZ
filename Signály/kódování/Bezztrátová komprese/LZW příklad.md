#příklad 
# Příklady

## Příklad komprese
Řetězec `abcabcabcbcba` (13 znaků), vstupní abeceda (použité znaky): a b c

### Postup
Přiřazení čísel a = 1, b = 2, c = 3
1. Nalezení nejdelší fráze ze slovníku shodné se vstupem, index na výstup, odebrání
2. Nová fráze = nalezená fráze + jeden další znak

| Krok | text vstupu | nalezená fráze | výstup | nová fráze | Index nov. fráze | 
|---|---|---|---|---|---|
|1 | abcabcabcbcba| a | 1 | ab | 4 |
| 2 | bcabcabcbcba| b | 2 | bc | 5 |
| 3 | cabcabcbcba | c | 3 | ca | 6 |
|4|abcabcbcba|ab|4|abc|7 |
|5|cabcbcba|ca|6|cab|8 |
|6|bcbcba|bc|5|bcb|9 |
|7 |bcba|bcb|9|
|8|a|a|1|
### Řešení
Výstup: řetězec `12346591` (8 čísel), kompresní poměr 61,5%

## Příklad dekomprese
Řetězec `12346591`, přiřazení čísel a = 1, b = 2, c = 3

### Postup
1. K číslu přiřazená fráze
2. Nová fráze = fráze z předchozího kroku + první znak fráze výstupu
Pokud číslo na vstupu je větší než současné číslo ve vytvářeném slovníku: výstup = nová fráze = minulá fráze + její první znak

| Krok | vstup | výstup | nová fráze | Index nov. fráze |
|---|---|---|---|---|
|1|1|a|
|2|2|b|ab|4|
|3|3|c|bc|5|
|4|4|ab|ca|6|
|5|6|ca|abc|7|
|6|5|bc|cab|8|
|7|9|bcb|bcb|9|
|8|1|a|
### Řešení
Výstup: řetězec `abcabcabcbcba`

## Příklad komprese

Aplikujte algoritmus LZW na zprávu nad abecedou A,B. Zpráva je `BABAABBAAAB`. První dvě položky slovníku budou A = 1, B = 2. Jak bude vypadat komprimovaná zpráva (v číslech položek slovníku)? Jak bude vypadat slovník na konci?

### Řešení

Zpráva po komprimaci: `213454`   
Slovník na konci: A=1,B=2,BA=3,AB=4,BAA=5,ABB=6,BAAA=7

## Příklad dekomprese

Na zprávu nad abecedou A,B,C byl aplikován algoritmus LZW. Komprimovaná zpráva - v číslech slovníkových položek je: `31124253`. Počáteční položky slovníku jsou A = 1, B = 2, C = 3. Jaká je nekomprimovaná zpráva? Jak bude vypadat slovník na konci?

### Řešení

Původní zpráva: `CAABCABAAC`  
Slovník na konci: A=1,B=2,C=3,CA=4,AA=5,AB=6,BC=7,CAB=8,BA=9,AAC=10