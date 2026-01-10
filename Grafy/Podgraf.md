# Podgraf
Řekneme že graf $G_1 = (V_1, H_1)$ je podgrafem grafu $G=(V,H)$, jestliže:
- $V_1 \subset V \land H_1 \subset H$

Tak že:
- $H_1 \subset \{\{u,v\}|u,v \in V_1\}$

> [!note]
> Hrany v podgrafu musí mít své vrcholy.
## Faktor:
$G_1 = (V_1, H_1)$ je faktor $G = (V,H)$, jestliže $V_1 = V \land H_1 \subset H$.

> [!tip]
> Některé hrany z grafu "chybí".

> [!info]
Kostra grafu je také jeho faktorem.
 
## Indukovaný podgraf:
$G_1 = (V_1, H_1)$ je indukovaný podgraf $G= (V,H)$ jestliže:
- $V_1 \subset V \land H_1 = H \cap \binom{V_1}{2}$
$=\{h \in H | h = \{u,v\} \land u,v \in V_1\}$

> [!tip]
> Vyhodíme některé vrcholy, necháme hrany, které mají smysl.

## Příklady
G:
```text
o --- o
| \ / |
|  o  |
| / \ |
o --- o
```

Podgraf:
```text  
o
|
|  o
| /
0 --- 0
```