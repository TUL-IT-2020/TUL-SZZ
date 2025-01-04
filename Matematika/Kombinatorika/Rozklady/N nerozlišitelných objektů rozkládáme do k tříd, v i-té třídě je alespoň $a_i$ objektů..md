### N nerozlišitelných objektů rozkládáme do k tříd, v i-té třídě je alespoň $a_i$ objektů.

$$
x_1 + x_2 + ... + x_k = n
$$
- $0 \leq a_i \leq x_i$

Odpovídá počtu řešení diofantické rovnice.

$$
\sum_{i=1}^k a_i \leq n
$$
Převod na binární řetězce:
- Přihrádky: $(k-1)*0$
- Zbude po povinném naplnění skupin: $(n - \sum_{i=1}^k a_i) * 1$

$$
P\left(k-1, n-\sum_{i=1}^k a_i\right) = C_{n+k-1-\sum_{i=1}^k a_i}^{k-1}
$$