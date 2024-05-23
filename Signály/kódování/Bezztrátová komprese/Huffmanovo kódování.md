# Huffmanovo kódování
Algoritmus navržen Davidem Huffmanem (1952)
Využití prefixového kódu - kód žádného znaku není prefixem jiného znaku, neprefixový kód: Morseova abeceda: A (.-), M(--), J(.---)
Proměnná délka kódových slov >>> „znaky“, které jsou nejvíce četné mají nejkratší délku a naopak: 111011011, A (0), E(10), G(11)

(+) Výhody – rychlá komprese a dekomprese, nenáročné na paměť
(-) Nevýhody – nutnost nalezených kódů, menší kompresní poměr
## Algoritmus kódování:
1. Zjištění četnosti jednotlivých „znaků“
2. Vytvoření jednotlivých kódů na základě četností
3. Nahrazení jednotlivými znaků v datovém souboru nalezenými kódy
### Huffmanova konstrukce
Zdrojová abeceda: A-E
p(A) = 0.15
p(B) = 0.1
p(C) = 0.15
p(D) = 0.35
p(E) = 0.25

1) seřadíme zdrojovou abecedu sestupně dle pravděpodobnosti výskytu (druhé řazení případně abecedně)

| Znak   | Pravděpodobnost |
| --- | ---- |
| D    | 0,35     |
| E   | 0,25     |
| A   | 0,15     |
| C   | 0,15 |
| B   | 0,1  |
2) Postupně spojujeme vrcholy s nejmenším výsledným součtem (odspodu)
	- Horní hraně vždy přidělujeme hodnotu 0 a dolní 1.
``` mermaid
flowchart LR
	Av((0.15))
	Bv((0.1))
	Cv((0.15))
	Dv((0.35))
	Ev((0.25))

	A---Av
	B---Bv
	C---Cv
	D---Dv
	E---Ev

	Cv ---|0| F((0.25))
	Bv ---|1| F

	Av ---|0| G((0.4))
	F ---|1| G

	Dv ---|0| H((0.6))
	Ev ---|1| H

	H ---|0| I((1))
	G ---|1| I
```

3) Sestavíme převodní tabulku
	- Při přepisování kódu postupujeme vždy od kořene stromu 

| Znak | Kód |
| ---- | --- |
| A    | 10  |
| B    | 111 |
| C    | 110 |
| D    | 00  |
| E    | 01  |

Průměrná délka
$L_{AV} = 0.15 *2  + 0.1 *3 + 0.15 * 3 + 0,35 *2 + 0.25 *2 = 2.25$
## Nejednoznačnost H.K.
Když vyjdou stejné pravděpodobnosti u určitých znaků.

### 2. Příklady
| Znak | Pravděpodobnost |
| ---- | ---- |
| A | 0,1 |
| B  | 0,1 |
| C  | 0,2 |
| D  | 0,2 |
| E  | 0,4 |

B+A = 0,2

Co bude následovat teď ???
- (B+A) + C
- (B+A) + D
- D + C

Další krok ???
- ((B+A) + C) + E
- ((B+A) + D) + E
- (D + C) + E

Průměrná délka: 2,2

Délky:
- $1,4*2$
- $1,2,3,2*4$
- $3*2,2*3$

Problém s nejednoznačností řeší Huffmanova standardizovaná konstrukce.

## Problémy komprese H.K.
- Nutnost přenášet kódovací tabulku.
- Pracuje na znacích, ne dvojicích, slovech
- statistický model pravděpodobnosti výskytu znaků
- když nepomůže "neublíží"

## Příklad
[[Huffmanovo kódování příklad]]

