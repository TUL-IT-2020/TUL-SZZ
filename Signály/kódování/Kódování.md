# Kódování 
Výklad významu jedniček a nul.
## Kódování jednoho znaku:
Zobrazení $K : A \to B^*$
- $A$ - zdrojová abeceda, př: $A = \{a,b,...,z\}$ 
- $B$ - kódová abeceda, př: $B = \{0,1\}$
- $^*$ - iterace množiny, př: $B^* = \{ \varnothing,0,1,00,01,10,11,...\}$
Kódová slova: Prvky z $B^*$, kterým je přiřazeno nějaké $a \in A$.
$b = K(a)$

## Kódování zprávy:
Zpráva: $M = a_1, a_2, a_3, ..., a_n \; a \in A$
Zakódovaná zpráva: $K(M) = K(a_1), K(a_2), K(a_3), ..., K(a_n)$

Příklad:
$A = \{a,b,c\}$
$B = \{0,1\}$

|     | $K_1$ | $K_2$ | $K_3$ | $K_4$ | $K_5$ |
| --- | ----- | ----- | ----- | ----- | ----- |
| a   | 0     | 0     | 00    | 01    | 0     |
| b   | 0     | 1     | 01    | 001   | 10    |
| c   | 1     | 01    | 10    | 0001  | 110   |
| d   | 11    | 11    | 11    | 00001 | 111   |

- $K_1$ - Singulární kód - není prostý
- $K_2$ - není jednoznačně dekódovatelný
- $K_3$ - blokový, stejně dlouhá bloková slova
- $K_4$ - různě dlouhá bloková slova, (jedničky slouží jako oddělovače)

$K_3,K_4,K_5$ - jsou instantní kódy (okamžité), lze je dekódovat jak postupně kódy přichází.

## Instantní kódy
![[Instantní kódy]]
## Bezztrátová komprese dat
![[Bezztrátová komprese dat]]
## Bezpečnostní kódy

- [[Bezpečnostní kódy]]
	- [[Reed Solomonovy kódy]]

## Další
[[Grayovy kódy]]
[[Konvoluční kódy]]