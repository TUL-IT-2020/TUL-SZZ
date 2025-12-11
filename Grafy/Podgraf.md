# Podgraf
Řekneme že graf $G_1 = (V_1, H_1)$ je podgrafem grafu $G=(V,H)$, jestliže:
- $V_1 \subset V \land H_1 \subset H$

## Faktor:
$G_1 = (V_1, H_1)$ je faktor $G = (V,H)$, jestliže $V_1 = V \land H_1 = H$.
Některé hrany chybí.
Kostra grafu je také jeho faktorem.
 
## Indukovaný podgraf:
$G_1 = (V_1, H_1)$ je infukovaný podgraf $G= (V,H)$ jestliže:
- $V_1 \subset V \land H_1 = H \cap \binom{V_1}{2}$
$=\{h \in H | h = \{u,v\} \land u,v \in V_1\}$