# JPEG – DCT II
Diskrétní kosinová transformace (DCT II)
využívá popisu signálu pomocí funkce cos

Obraz rozdělen na bloky 8×8
Zápis lze přepsat maticově

Inverzní transformace

![[DCT.png]]
## Kvantizace
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

## zigzag, RLE, Huffmann
Zajímavé koeficienty jsou v levé horní polovině obrazu. 
Po kvantizaci by měla být pravá dolní polovina plná nul.

![[JPEG - zigzag.png]]

Opakující se znaky jsou komprimovány RLE.
U JPEG se udává ve formátu XY
Počet nul
Jiná než nulová hodnota

Huffmanovo kódování
DC koeficienty zvlášť

Latence výpočtu
obrázek + nutnost přenést tabulku znaků
8 řádků + typ předpřipravené tabulky znaků