### N nerozlišitelných objektů do rozlišitelných tříd
[[Diofantická rovnice příklad]]

> [!tip]
Počet rozkladů $n$ nerozlišitelných objektů do k rozlišitelných tříd. Třída může zůstat prázdná. Je roven počtu celočíselných řešení diofantické rovnice $x_1 + ... + x_k = n$.
- $\forall i \; x_i \in N$

- $x_i$ - počet prvků v $i$-té třídě 

Dvě různá řešení:
(1,0,...,n-1)
(n-1,0,...,1)

Bitové řetězce:
$x_1 + x_2 + ... + x_k = n$

Místo každého $+$ (oddělovače) dáme $0$.
$x_1 0 x_2 0 ... 0 x_k = n$
Místo počtu prvků v jednotlivých rozkladech umísťujeme $1$.
Do každé přihrádky dáme tolik jedniček, kolik je tam prvků. 

Počet $0,1$:
- $n*1$
- $(k-1)*0$


$$
P(n,k-1) = C_{n+k-1}^{k-1}
$$