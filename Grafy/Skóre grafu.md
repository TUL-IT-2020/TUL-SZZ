# Skóre grafu

## Stupeň vrcholu
![[Stupeň vrcholu]]

## Skóre grafu

> [!tip]
Posloupnost stupnů jednotlivých vrcholů.

$|V| = n$
$(d_1,d_2,...,d_n)$ ... grafová posloupnost, skóre grafu.
- $d_1 \geq d_2 \geq ... \geq d_n$

$v \in V$
$0 \leq d(v) \leq |V| -1$

> [!info] Skóre grafu nedefinuje graf jednoznačně.

> [!tip] V každém jednoduchém grafu vždy existují alespoň dva vrcholy, které mají stejný stupeň.

$G = (V,H)$ je jednoduchý graf. Potom platí:
- $\forall v \in V$ -> $0 \leq d(v) \leq |V-1|$
- $\exists u,v \in V \; u \ne v \land d(u) = d(v)$

> [!note] Důkaz (sporem):
Nechť každý vrchol má jiný stupeň.
Možné ohodnocení: $\{0,1,...,n-1\}$, máme $n$ vrcholů.
- $d(v_k) = n-1$ ... musí mít hranu se všemi ostatními,
- $d(v_0) = 0$ ... ale předpokládali jsme existenci samostatného vrcholu.
=> SPOR

> [!tip] V každém multigrafu je počet uzlů lichého stupně sudý. 
(každá hrana je tvořena dvěma vrcholy...)

$G = (V,H)$ je multi graf. Potom platí:
$$
2|H| = \sum_{v \in V} d(v)
$$
### Havlův algoritmus

![[Havlův algoritmus]]