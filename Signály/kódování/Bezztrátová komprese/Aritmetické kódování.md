# Aritmetické kódování
Zadané pravděpodobnosti:
p(A) = 0.4
p(B) = 0.35
p(C) = 0.25

Huffman : A - jednoznakové nebo dvou znakové
Buď nevyužítí prosotru nebo "přetížení"
Ideální: K.S. pro A : $-\log_2(0.4) = 1.32 \;bit$

Zakódovaná zpráva - číslo z <0,1>
Zpráva: ABBC

| Příchozí znak | počátek intervalu | znak | pravděpodobnost | znak | pravděpodobnost | znak | konec intervalu |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| A | 0 | A⬇️ | 0,4 | B | 0,25 | C | 1 |
| B | 0 | A | 0,16 | B⬇️ | 0,3 | C | 0,4 |
| B | 0,16 | A | 0,22 | B⬇️ | 0,256 | C | 0,3 |
| C | 0,22 | A | 0,2344 | B | 0,247 | C⬇️ | 0,256 |
Výsledné číslo je například: 0,25 (číslo mezi 0,247 a 0,256 s nejmenším počtem desetinných pozic)

Problémy A.K.:
- meze se sbližují - limitace přesnosti datových typů
	- Můžeme začít přenášet ta čísla která se s jistotou nezmění a můžeme je "odečíst" je od našeho vypočítaného intervalu.
- podtečení znaků s malou pravděpodobností
	- p(D) = $10^{-9}$
	- Zpráva ADB ...., interval ($0.3-10^{-9}$; $0.3$)

> Je to dobré, ale nikdo to nepoužívá.
>  - Otto Severýn

## Příklady
- [[Aritmetické kódování příklad]]