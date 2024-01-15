# Redukovaná soustava zbytků
## Příklad
$Z^*_{18}$ ... Redukovaná soustava zbytků modulu 18

1) Vypište všechny její prvky.
2) Rozhodněte zda tvoří cyklickou grupu?
3) Určete všechny její generátory.
### Postup
1) Vypište všechny její prvky:
$\varnothing \neq Z^*_{18} \subset Z_m$
Rozklad: $18 = 2*3^2$ ... nesmí být v rozkladu prvků množiny 
$\varphi(18) = (2^1-2^0)(3^2-3^1) = 6$ ... bude jich
Zbytky nesoudělné s modulem:
$Z^*_{18} = \{1,5,7,11,13,17\}$

2) Rozhodněte zda tvoří cyklickou grupu?
- $(Z_{m},+)$ ... aditivní grupa
- $(Z^*_{18},+)$ ... není grupa
  1+5 mod(18) = 6 ... není prvek redukované soustavy zbytků
- $(Z^*_{18},*)$ ... inverzní prvky existují, tvoří grupu

3) Určete všechny její generátory: $<x> =? Z^*_{18}$

| $n^1(18)$ | 1 | 5 | 7 | 11 | 13 | 17 |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| $n^2(18)$ | 1 | $5*5(18)=7$ | 13 | 13 | 7 | 1 |
| $n^3(18)$ |  | $7*5(18)=17$ | 1 | 11 | 1 |  |
| $n^4(18)$ |  | $17*5(18)=13$ |  | 7 |  |  |
| $n^5(18)$ |  | $13*5(18)=11$ |  | 5 |  |  |
| $n^6(18)$ |  | $11*5(18)=1$ |  | 1 |  |  |
$Z^*_{18} = <5> = <11>$ ... generátory
$<13> = <7>$ 
