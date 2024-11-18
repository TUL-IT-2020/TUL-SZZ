# N nerozlišitelných objektů rozkládáme do nerozlišitelných tříd
> [!tip]
Počet rozkladů n nerozlišitelných rozkladů objektů do nerozlišitelných tříd (všechny možnosti možných počtů tříd) je roven:
- Počtu rozkladů přirozeného čísla n na kladné sčítance.
- Počtu řešení diofantické rovnice $x_1 + 2x_2 + ... nx_n = n$.
	- $\forall i \; x_i \in N$
- Počet rozkladů přirozeného čísla $n$ na sčítance rovné některým z čísel $a_1,...,a_k$ (předepisujeme počty prvků v jednotlivých třídách, předepisujeme velikosti sčítanců)

$n = 1 + ... + 1$
Sčítání je komutativní:
$1+2 = 2 +1$

> [!note] Sčítance budeme vypisovat od nejmenšího po největší.

- $x_i$ - počet sčítanců velikosti i (počet skupin velikosti i)


Počet řešení diofantické rovnice
$$
a_1x_1 + ... + a_kx_k = n
$$
- $\forall i \; x_i \in N$

n = 353
a_1 = 12
a_2 = 33
a_3 = 42

Nelze vyřešit tuto diofantickou rovnici.
Podmínka:
$NSD(a_1,...,a_k) | n$

Vytvořující funkce:

$$
x_1 + 2x_2 + ... nx_n = n
$$
$(1+x+x^2+...)$
1/1-x

$(1+x^2+x^4+...)$
1/1-x^2

$(1+x^n+x^{2n}+...)$
1/1-x^n

$$
f(x) = \prod_{i=1}^k \frac{1}{1-x^{i}}
$$

$$
a_1x_1 + ... + a_kx_k = n
$$

$$
f(x) = \prod_{i=1}^k \frac{1}{1-x^{a_i}}
$$
> [!question]
Každý ze sčítanců lze použít pouze jednou.

$$
f(x) = \prod_{i=1}^k (1 + x^{a_i})
$$
