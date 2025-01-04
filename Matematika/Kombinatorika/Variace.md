
# Variace
## Variace bez opakování
n - různých prvků
variace k-té třídy = uspořádaná k-tice prvků z n.
 $A^k_n$ - počet variací k-třídy z n-prvků

$$
A^k_n = n(n-1) * ... * (n-k+1) = \frac{n!}{(n-k)!}
$$
- $0 \leq k \leq n$

Důkaz:

| Výběr       | 1.  | 2.  |     | k.    |
| ----------- | --- | --- | --- | ----- |
| Počet prvků | n   | n-1 | ... | n-k+1 |
Pravidlo součinu

## Variace s opakováním
Máme k dispozici n různých prvků, každý v neomezeném počtu. 
Tedy variace k-té třídy s opakováním. Sestavujme uspořádané k-tice prvků, prvky se mohou opakovat.

> [!note]
Sestavujeme slova nad abecedou.

$\bar A ^k_n$ - počet variací k-té třídy z n prvků s opakováním

- $0 \leq k,n$

## Generování Variací
![[Generování variací]]
