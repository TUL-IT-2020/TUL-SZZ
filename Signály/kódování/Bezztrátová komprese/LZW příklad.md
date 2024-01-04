#příklad 
# Příklady
## Příklad 

Aplikujte algoritmus LZW na zprávu nad abecedou A,B. Zpráva je BABAABBAAAB. První dvě položky slovníku budou A = 1, B = 2. Jak bude vypadat komprimovaná zpráva (v číslech položek slovníku)? Jak bude vypadat slovník na konci?

### Řešení

Zpráva po komprimaci: 213454   
Slovník na konci: A=1,B=2,BA=3,AB=4,BAA=5,ABB=6,BAAA=7

## Příklad

Na zprávu nad abecedou A,B,C byl aplikován algoritmus LZW. Komprimovaná zpráva - v číslech slovníkových položek je: 31124253. Počáteční položky slovníku jsou A = 1, B = 2, C = 3. Jaká je nekomprimovaná zpráva? Jak bude vypadat slovník na konci?

### Řešení

Původní zpráva: CAABCABAAC  
Slovník na konci: A=1,B=2,C=3,CA=4,AA=5,AB=6,BC=7,CAB=8,BA=9,AAC=10