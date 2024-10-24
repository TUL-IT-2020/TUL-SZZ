# Rekurentní vztahy

> [!note] Latinsky
> rekurere - vraceti se

Počáteční podmínky (analogie ukončovací podmínky u algoritmů)

Definice:
Nechť $\{a_n\}^\infty_{n=0}$ je posloupnost. Rekurentním vztahem pro posloupnost  $\{a_n\}^\infty_{n=0}$ nazýváme výraz:
$$F (a_n, a_n-1, ..., a_0, n) = 0$$, kde $F$ je funkce proměnných $(a_n, a_n-1, ..., a_0, n)$ taková, že:
$\forall n >= n_o$, který umožňuje určit hodnotu $a_n$ na základě znalosti hodnot:
- $a_0, a_1, a_2, n_0$

Řešením rekurentního vztahu rozumíme libovolnou posloupnost $\{a_n\}^\infty_{n=0}$, takovou že $\forall n >= n_o$  po dosazení hodnot $(a_n, a_n-1, ..., a_0, n)$ platí $F (a_n, a_n-1, ..., a_0, n) = 0$.

## Základní klasifikace rk. vztahů
- homogenní (nulová posloupnost je řešením)
- nehomogenní 

- lineární (funkce $F$ je lineární funkcí proměnných $(a_0, a_1,.., a_n)$)
- nelineární

### Příklady
![[Rekurentní vztahy příklady]]

## Dále:
- [[Homogenní lineární rekurentní vztahy]]
- [[Nehomogenní lineární rekurentní vztahy]]