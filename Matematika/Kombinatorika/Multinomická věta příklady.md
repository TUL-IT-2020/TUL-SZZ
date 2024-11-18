# Multinomická věta


## Příklad

$$
(u-2v^2+3w-\frac{\sqrt{x}}{2}-3y^3)^{7}
$$

Určete koeficient u $u^2w^2xy^3$.

### Postup
$$
(x_1 + x_2 + x_3 +...+ x_n)^{n} = \sum_{n_1,n_2,...,n_k} P(n_1,n_2,...,n_k) * x_1^{n_1} * x_2^{n_2} * ... * x_k^{n_k}
$$

- $n_i \geq 0$
- $\sum_{i=1}^{k} n_i = n$

Vyskytuje se tento člen v násobení?


| $u$ | $v^2$ | $w$ | $x^{1/2}$ | $y^3$ | Koeficient | 7 |
| --- | ----- | --- | --------- | ----- | ---------- | - |
| 2 |0|2|2|1| suma | 7 |

Člen se vyskytuje v násobení.

### Řešení

$$
P(7,0,2,2,1) * 1^{2} * 3^{2} * (-1/2)^{2} * (-3) =
\frac{7!}{2!2!1!} * ...
$$
## Příklad
$$
(2u +x^2 - 3y + \sqrt{2z})^{7}
$$

Má nenulové koeficienty u členů:
- $x^2y^4z$
- $ux^2yz^2$
- $u^4x^2yz^{1/2}$

### Postup

| $u$ | $x^2$ | $y$ | $\sqrt{z}$ | Koeficient | 7 |
| --- | ----- | ----- | --- | ---------- | - |
| 0 | 1 | 4 | 2 | suma | 7 |
| 1 | 1 | 1 | 4 | suma | 7 |
| 4 | 1 | 1 | 1 | suma | 7 |

### Řešení
Ano, všechny členy se vyskytují v násobení.