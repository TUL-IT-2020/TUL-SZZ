# Stirlingova čísla 1. a 2. druhu

$$
x^\underline{n} = x(x-1)*...*(x-n+1)
$$
- $x \in R$
- $n \in N$

- falling power / pochhammor symbol
- padající faktoriál

Vyjde nám polynom
$$
x^\underline{n} = \sum_{k=0}^n s(n,k) x^k
$$
- $s(n,k)$ - Stirlingova čísla prvního druhu
$$
s(n,k) = (-1)^{n-k} 
\left[ 
\begin{array}{c} n \\ k \end{array}
\right]
$$

$$
x^n = \sum_{k=0}^n  S(n,k)*x^\underline{n}
$$
- $S(n,k)$ - Stirlingovo číslo 2.druhu

$$
S(n,k) = \left\{\begin{array}{c} n \\ k \end{array}\right\}
$$