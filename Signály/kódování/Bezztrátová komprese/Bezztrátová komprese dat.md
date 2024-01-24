# Bezztrátová komprese dat
``` mermaid
flowchart LR
	M((*))
	M-- "M" -->C[C]
	C-- "M^C" -->C_1["C^-1"]
	C_1-- "M" -->M_2((*))
```
- $M$ - je daná zpráva
- $L(M) \ge L(M^c)$ - Délka původních dat je větší než komprimovaných.
- Kompresní poměr: $\frac{L(M)}{L(M^c)}\ge 1$
	- Kolikrát se data zmenší
- Kompresní faktor: $\frac{L(M^c)}{L(M)}\le 1$
	- Na kolik % se data zmenší
- Limit: entropie $M$

## Kolmogorovská složitost:
Délka nejkratšího programu který vypíše daný řetězec. 
Tento přístup ke složitosti objektů (a tím také ke komprimaci dat) popsal v roce 1963 sovětský matematik Andrej Nikolajevič Kolmogorov.

Např: `abababababab...` má menší složitost než: `xc18;AHkQ9`

Je v datech vzor?
- 010011000111 - nejspíše ano
- 010011111000 - možná ne

## Přístupy komprese:
- Statistické ([[Huffmanovo kódování|Huffmanovo kódování]])
- RLE
- Slovníkové

### Huffmanovo kódování
![[Huffmanovo kódování]]
### Aritmetické kódování
![[Aritmetické kódování]]

### RLE - run length encoding
![[RLE - run length encoding]]

### Slovníkové metody
![[Slovníkové metody - LZ]]

### BWT (Burrows-Wheelerova Transformace)
![[BWT (Burrows-Wheelerova Transformace)]]

### MTF (Move-To-Front)
![[MTF (Move-To-Front)]]