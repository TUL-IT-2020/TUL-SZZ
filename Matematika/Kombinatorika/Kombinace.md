# Kombinace
- $n$ různých prvků
Kombinace k-té třídy = neuspořádaná k-tice prvků

(a,b,c) = (b,c,a)
{a,b,c} = {b,c,a}

## bez opakování
$c^k_n$ ... počet kombinací řádu k z n prvků bez opakování

$(n k)$  ... n nad k

$A^k_n = k!C^k_n$

$$
C^k_n = \frac{n!}{(n-k)!k!}
$$
- $0 \leq k \leq n$

Platí:
$C^k_n= C^{n-k}_n$ ... symetrie

$C^k_n=C^k_{n-1} + C^{k-1}_{n-1}$ ... Pascalova identita

$C^k_n = P(k,n-k)$

$\sum^n_{k=0} C^k_n = 2^n$
- $(1+1)^n$
$\sum^n_{k=0} (-1)^k C^k_n = 0$
- $(1-1)^n$

## Kombinace s opakováním
n různých prvků, každý v libovolném počtu.
Sestavujeme neuspořádané k-tice, ve kterých se mohou prvky opakovat.

$\bar C^k_n$ ... počet kombinací k-té třídy z n prvků s opakováním

$$
\bar C^k_n = P(k, n-1) = C^k_{n+k-1}
$$
- $0 \leq k,n$

Každou kombinace lze zakódovat do bitového řetězce s:
- $(n-1)*0$
- $k*1$

## Generování kombinací
![[Generování kombinací]]