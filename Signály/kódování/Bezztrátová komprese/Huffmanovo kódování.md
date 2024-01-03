# Huffmanova konstrukce
Zdrojová abeceda: A-E
p(A) = 0.15
p(B) = 0.1
p(C) = 0.15
p(D) = 0.35
p(E) = 0.25

``` mermaid
flowchart RL
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

	Cv ---|1| F((0.25))
	Bv ---|0| F

	Av ---|1| G((0.4))
	F ---|0| G

	Dv ---|1| H((0.6))
	Ev ---|0| H

	G ---|1| I((1))
	H ---|0| I
```

| Znak | Kód |
| ---- | --- |
| A    | 01  |
| B    | 000 |
| C    | 001 |
| D    | 11  |
| E    | 10  |

Průměrná délka
$L_{AV} = 0.15 *2  + 0.1 *3 + 0.15 * 3 + 0,35 *2 + 0.25 *2 = 2.25$
## Nejednoznačnost H.K.
Když vyjdou stejné pravděpodobnosti u určitých znaků.

### 2. Příklad
A 0,1
B 0,1
C 0,2
D 0,2
E 0,4

B+A = 0,2

???
(B+A) + C
(B+A) + D
D + C

???
((B+A) + C) + E
((B+A) + D) + E
(D + C) + E

Průměrná délka: 2,2

Délky:
$1,4*2$
$1,2,3,2*4$
$3*2,2*3$

## Problémy komprese H.K.
- Nutnost přenášet kódovací tabulku.
- Pracuje na znacích, ne dvojicích, slovech
- statistický model pravděpodobnosti výskytu znaků
- když nepomůže "neublíží"