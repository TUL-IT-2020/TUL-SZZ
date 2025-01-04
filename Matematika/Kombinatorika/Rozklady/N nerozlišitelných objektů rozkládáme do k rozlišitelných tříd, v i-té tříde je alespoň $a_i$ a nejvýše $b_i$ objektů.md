# N nerozlišitelných objektů rozkládáme do k rozlišitelných tříd, v i-té tříde je alespoň $a_i$ a nejvýše $b_i$ objektů

- $0 \leq a_i \leq b_i \leq x_i$

$$
\sum_{i=1}^k a_i \leq n
$$Odpovídá počtu řešení diofantické rovnice.

$$
x_1 + x_2 + ... + x_k = n
$$
- $\forall i (0 \leq) a_i \leq x_i \leq b_i$

Komplikuje nám to horní mez.
Řešíme pomocí: princip inkluze a exkluze

1. Převedeme úlohu do standardizovaného tvaru.

Odečteme $a_i$

$$
0 \leq x_i - a_o \leq b_i - a_i
$$
$$
0 \leq y_i \leq c_i
$$
$y_1 + ... + y_k = m$
- $\forall i \; 0 \leq y_i \leq c_i$
- $m = n - \sum_{i=1}^k a_i$

Počáteční podmínky:
- $\alpha_1: c_1+1 \leq y_1$
- $\alpha_2: c_2+1 \leq y_2$
- ...
- $\alpha_k: c_k+1 \leq y_k$
$$
N(\bar \alpha_1, \bar \alpha_2, ..., \bar \alpha_k) =
N - 
\sum_{i=1}^k N(\alpha_i) + 
\sum_{i\leq i_1 \leq k} N(\alpha_{i_2}, \alpha_{i_2}) -
\sum_{i\leq i_1 \leq i_2\leq i_3\leq n}^k N(\alpha_i) + 
... +
(-1)^k N(\alpha_1, \alpha_2, ..., \alpha_k)
$$


$N =P(k-1,n)$
$N(\alpha_i) = P(k-1,n-(c_i+1))$
$N(\alpha_{i_1}, \alpha_{i_2}) = P(k-1,n-(c_{i_1}+1)-(c_{i_2}+1))$
...
$N(\alpha_{i_1}, \alpha_{i_2}, \alpha_k) = P(k-1,n-\sum _ {i=1} ^k c_i -k)$
