# Homogenní lineární rekurentní vztahy  

> [!tip]
Homogenní lineárním rekurentními vztahem řadu $k$ s konstantními koeficienty rozumíme výraz:  
$$
c_k a_{n+k} + c_{k-1} a_{n+k-1} + ... + c_0 a_n = 0  
$$
> [!example] Kde:  
- $c_i \in R (i= 0, ...,k)$ a zároveň 
- $c_0,c_k$ není 0  

Tedy nulová posloupnost je řešením rekurentního vztahu.

> [!danger] HLR(\*)

Řešením HLR(\*) rozumíme libovolnou posloupnost $a_n$ takovou že pro každé $n\in N$ po dosazení do HLR(\*) platí rovnost.  

Takže je to soustava nekonečně mnoha rovnic.

Platí:
HLR(\*) má nekonečně mnoho řešení. Jestliže předepíšeme k počátečních podmínek, tj: libovolných $k$ po sobě jdoucích hodnot, potom existuje jediné řešení, které jim vyhovuje.

> [!note] Počáteční hodnoty 
> Obvykle:
> $$(a_0,..,a_k)$$

Množina všech řešení HLR tvoří vektorový prostor dimenze k.

$$
a_{n+k} = \frac{-1}{c_k}(c_{n-1}a_{n+k-1}+...+c_1a_n)
$$

Nulový prvek (vektor nul):
$$
\{0\}^\infty_n=0
$$
Lineární kombinace řešení HLR je také řešením. ERGO lineární prostor.
$$
\{a_n^{(1)}\};\{a_n^{(2)}\}
$$
je řešením HLR, $k_1, k_2 \in R$

->
$$
\{K_1a_n^{(1)} + K_2a_n^{(2)}\}
$$
je tedy také řešením HLR.

> [!tip] Důsledek:
Řešit HLR znamená nalézt $k$ lineárně nezávislých řešení. (báze, obecné řešení)

## Obecné řešení:
Lineární kombinace výše uvedených $k$ lineárně nezávislých řešení.


> [!question] Otázka:
Jak nalézt řešení HLR?
(Jak nalézt bázi)

### Charakteristický polynom HLR(\*):
Převedeme všechny členy na levou stranu a členy $a_n$ nahradíme za $x^{k-n}$.
$$
C_kx^k + C_{k-1}x_{k-1} +...+C_{1}x_+C_0
$$

Platí:
Necht $r_1,...,r_l$ jsou všechny různé kořeny charakteristického polynomu HLR a $m_1,...,m_l$ jsou jejich násobnosti.

$(m_1+m_2+...+m_l = k)$
- $k$ je násobnost (počet kořenů)

Potom obecné řešení HLR má tvar:

$$
a_n = r_1^n(K_1^{(1)} +K_2^{(1)}n+...K_{m_1}^{(1)}n^{m_1-1}) +
...+
r_l^n(K_1^{(l)} +K_2^{(l)}n+...K_{m_l}^{(l)}n^{m_l-1})
$$
kde:
- $K_1^{(1)}, ..., K_{m_l}^{(l)}$ jsou libovolné konstanty (celkem $k$ konstant)

### Vícenásobné kořeny
Kořen $r$ násobnosti $m$ vygeneruje $m$ lineárně nezávislých řešení: 
$$
\{r^n\}^\infty_{n=0}, \{nr^n\}^\infty_{n=0}, ..., \{n^{m-1}r^n\}^\infty_{n=0}
$$

### Komplexně sdružené kořeny
![[Komplexní čísla]]

2 komplexně sdružené kořeny:
$$
a_n = K_1(a+b_i)^n + K_2(a-b_i)^n
$$
Komplexní čísla:
$$
(a \pm b_i)^n
$$
Na 2 posloupnosti:
- $\sqrt{a^2 + b^2}(\cos n\varphi)$
- $\sqrt{a^2 + b^2}(\sin n\varphi)$

$x_{1,2} = re^{\pm j\varphi}$
$$
a_n^h​=K_1(​r)^ncos(n\varphi)+K_2(​r)^nsin(n\varphi).
$$

## Příklad:
- [[HLR příklady]]
