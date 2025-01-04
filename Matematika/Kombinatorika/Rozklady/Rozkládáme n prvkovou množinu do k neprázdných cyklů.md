# Rozkládáme n prvkovou množinu do k neprázdných cyklů
Prvky v třídách rozkladu jsou uspořádány na kružnici = cyklu.

$$
\left[ 
\begin{array}{c} n \\ k \end{array}
\right]
$$
= stirling cycle number řádu n,k

Počet rozkladů n-prvkové množiny do k neprázdných cyklů.

Počet permutací prvků na n prvkové množině, které jsou zapsány pomocí k disjunktních cyklů.

$$
\sum_{k=0}^n 
\left[ 
\begin{array}{c} n \\ k \end{array}
\right] 
= n!
$$

Základní hodnoty:

| n   | k   | =   | hodnota                    |                                                          |
| --- | --- | --- | -------------------------- | -------------------------------------------------------- |
| 0   | 0   |     | 1                          |                                                          |
| n   | 0   |     | 0                          |                                                          |
| n   | 1   |     | (n-1)!                     | počet permutací na n prvkové množině zapsané na 1 cyklem |
| n   | n-1 |     | $C^2_n = \frac{n(n-1)}{2}$ |                                                          |

$$
\left[ 
\begin{array}{c} n \\ k \end{array}
\right] =
\left[ 
\begin{array}{c} n-1 \\ k-1 \end{array}
\right] + 
(n-1)
\left[ 
\begin{array}{c} n-1 \\ k \end{array}
\right]
$$
- $(n-1)$ pozic kam ten prvek můžeme přidat

$a_1$:
- tvoří samostatný cyklus
- netvoří samostatný cyklus

#TODO: trojúhelník