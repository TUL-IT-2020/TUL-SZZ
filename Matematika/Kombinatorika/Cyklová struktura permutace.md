
> [!note] cycle-structure
> Výraz, který popisuje strukturu disjunktních cyklů permutace $\pi$.

> [!tip]
> Nechť P je množina permutací na $N = \{1,...,n\}$. Pro $\pi \in P$ definujeme cyklickou strukturu permutace jako formální výraz:

$$
x_1^{(\alpha_1)}*x_2^{(\alpha_2)}*...*x_n^{(\alpha_n)}
$$

> [!example] Kde:
>- $x_i$ - reprezentují cykly délky $i$
>- $\alpha_i$ - počet cyklů délky $i$


## Polynom cyklického indexu

"Průměr" cyklických struktur všech permutací v grupě G.

$\pi \in S_n = cyc\_str(\pi)$ 

Permutační grupa: $G= (X,P) \subset (Sn, *)$

> [!tip]
Každé $G=(X,P)$ lze přiřadit tzv. cycle-index polynomu:
$$
P_G(x_1, ..., x_n) = \frac{1}{|P|} \sum_{\pi \in P} cyc\_str(\pi)
$$

Kde:
- $|P|$ - řád permutace grupy, tedy počet prvků P.

## Příklady

$\pi =$ 
(1)(2)(3)(4)

$cyc\_str(\pi) = x_1^{(4)}$

$\pi =$ 
(1 2)(3 4)

$cyc\_str(\pi) = x_2^{(2)}$

$\pi =$ 
(1 2 3 4)

$cyc\_str(\pi) = x_4^{(1)}$
