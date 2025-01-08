# JPEG – DCT II
JPG (JPEG, přesněji JFIF) od: Joint Photography Experts Group, ukládání fotografií, hlavní formát pro prezentaci fotografií na webu, digitální fotoaparáty, ztrátový formát založený na diskrétní kosinové transformaci -> malé čtverečky o rozměrech 8x8 pixelů (rychlost), velká komprese -> viditelné artefakty tvaru čtverečků, kontury místo plynulých přechodů barev, vzorečky v oblastech s drobnou texturou, „duchové“ kolem hran; náhled z nízkých frekvencí.

> [!tldr] Diskrétní kosinová transformace (DCT II)
> Využívá popisu signálu pomocí funkce cos.
> Obraz rozdělen na bloky 8×8
> Zápis lze přepsat maticově
> Inverzní transformace

![[DCT.png]]

## Postup JPG komprese:
1) Převod do barevného prostoru YCbCr
2) Převzorkování (4:4:4, 4:2:2, 4:2:0) odstranění části barevné informace
3) Rozdělení obrázku do makrobloků 8x8
4) Výpočet DCT: Diskrétní kosinová transformace
5) Kvantizace pomocí kvantizační tabulky, zahození části informace – vysoké frekvence
6) Linearizace (zig-zag)
7) RLE kódování
8) Huffmanovo nebo aritmetické kódování
### Kvantizace
Kvantizace DCT složek
Vydělení celočíselnou maticí
V celočíselné aritmetice (fixed point násobení)
cílem je získat hodnoty vlevo nahoře a ztratit směrem dolů doprava

Kvantizační matice
Hodnoty matice určují výslednou kvalitu. Záleží na generátoru matice (psychovisuální model, příloha K).

Typicky škála 0-100:
- 95-100 nevýhodná vzhledem k výsledné velikosti
- 70-90 většinou není vidět
- 30-70 znatelné artefakty
- <30 
Pro chromatické složky jiné tabulky + podvzorkování

![[JPEG - kvalita.png]]

### zigzag
Zajímavé koeficienty jsou v levé horní polovině obrazu. 
Po kvantizaci by měla být pravá dolní polovina plná nul.

![[JPEG - zigzag.png]]

### RLE
Opakující se znaky jsou komprimovány RLE.
U JPEG se udává ve formátu XY
Počet nul
Jiná než nulová hodnota

### Huffmann
Huffmanovo kódování
DC koeficienty zvlášť

Latence výpočtu
obrázek + nutnost přenést tabulku znaků
8 řádků + typ předpřipravené tabulky znaků