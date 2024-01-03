# Bezztrátová komprese dat
``` mermaid
flowchart LR
	M((*))
	M-- "M" -->C[C]
	C-- "M^C" -->C_1["C^-1"]
	C_1-- "M" -->M_2((*))
```
- $M$ - je daná zpráva
- $L(M) \ge L(M^c)$ - Délka původních dat je menší než komprimovaných.
- Kompresní poměr: $\frac{L(M)}{L(M^c)}\ge 1$
	- Kolikrát se data zmenší
- Kompresní faktor: $\frac{L(M^c)}{L(M)}\le 1$
	- Na kolik % se data zmenší
- Limit: entropie $M$

Kolmogorovská složitost:
Délka nejkratšího programu který vypíše daný řetězec.

Např: abababababab... má menší složitost než: xc18;AHkQ9

Je v datech vzor?
- 010011000111 - nejspíše ano
- 010011111000 - možná ne

Přístupy komprese:
- Statistické (Huffmanovo kódování)
- RLE
- Slovníkové

## Aritmetické kódování
p(A) = 0.4
p(B) = 0.35
p(C) = 0.25

Huffman : A - jednoznakové nebo dvou znakové
Buď nevyužítí prosotru nebo "přetížení"
Ideální: K.S. pro A : $-\log_2(0.4) = 1.32 \;bit$

Zakódovaná zpráva - číslo z <0,1>
Zpráva: ABBC

0 A 0,4 B 0,25 C 1
A
0 - 0,4 0,25 1
B
0 0,16 - 0,3 0,4
B
0,16 0,22 - 0,256 0,3
C
0,22 0,2344 0,247 - 0,256

Výsledné číslo je například: 0,25

Problémy A.K.:
- meze se sbližují - limitace přesnosti datových typů
	- Můžeme začít přenášet ta čísla která se s jistotou nezmění a můžeme je "odečíst" je od našeho vypočítaného intervalu.
- podtečení znaků s malou pravděpodobností
	- p(D) = $10^{-9}$
	- Zpráva ADB ...., interval ($0.3-10^{-9}$; $0.3$)

> Je to dobré, ale nikdo to nepoužívá.
>  - Otto Severýn

## RLE - run length encoding
Počet opakování téhož znaku / fráze.

Zpráva: ABBBBAACCCA
Zákodujeme: A4B2A3CA

> Když nepomůže, neublíží.
>  - Otto Severýn
## Slovníkové metody
Statický slovník - moc nefunguje.
Dynamický slovník:
- LZ77
- LZ78
- LZW
	- L - Lempel
	- Z - Ziv
	- W - Welch

### LZ 77
Dvě okna, průběžně se posouvají.
Větší okno, menší okno.
Úsek v malém okně nahradíme odkazem do většího okna, kde hledáme výskyty.

| Velké okno                  | Malé okno      |
| --------------------------- | -------------- |
| She sells sea shells on     | the sea shore. |
| S[he se]lls sea shells on | "he se"        |
| She sells se[a sh]ells on | "a sh"         |

### LZ 78, LZW
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
