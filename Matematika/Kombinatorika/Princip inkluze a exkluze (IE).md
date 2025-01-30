# Princip inkluze a exkluze (IE)

$$
N(\bar \alpha_{1},....,\bar \alpha_{n}) = 
N - 
\sum_{i=1}^n N(\alpha_i) +
\sum_{1 \leq i_1 \leq i_2 \leq n} N(\alpha_{i1},\alpha_{i2})
+ ...
+ (-1)^k \sum_{1 \leq i_1 \leq i_2 \leq ... \leq n} N(\alpha_{i1},..,\alpha_{ik})
$$
> [!example] Kde:
- $N$ - celkový počet objektů
- $\alpha_1, ..., \alpha_n$ - potencionální vlastnosti objektů
- $N(\alpha_{i1},....,\alpha_{ik})$ - počet objektů z celkového počtu které mají vlastnosti uvedené v závorce
- $\alpha_{i1}$ - objekt s uvedenou vlastností
- $N(\bar \alpha_{1},....,\bar \alpha_{n})$ - počet objektů, které nemají žádnou vlastnost $\alpha_1, ...,\alpha_n$

$\bar A$ - doplněk množiny $A$

Průniku všech doplňků podmnožin množiny $A_i$ je roven rozdílu množiny $A_i$ a všech sjednocených jejích doplňků.

$$
\bigcap_{i=1}^n \bar{A_i} = A - \bigcup_{i=1}^n A_i
$$

![[venn4-2.png]]
## Zdroje:
- [wiki](https://cs.wikipedia.org/wiki/Princip_inkluze_a_exkluze)