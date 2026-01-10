# Souvislost grafů

## Souvislý graf
![[Souvislý graf]]
## Sled
Posloupnost vrcholů z $u$ do $v$, kde dvojice po sobě jdoucích vrcholů tvoří hranu.
- $n$ - délka sledu

$$
\forall i \in \{1,...,u \} \; \{u_{i-1}, u_i\}
$$

- $u = v$ - uzavřený sled

> [!note]
> Vrcholy i hrany se mohou opakovat.
## Tah
"Optimálnější způsob jak se dostat z u do v."
Hrany se v tahu nesmí opakovat. 

## Cesta
Vrcholy se nesmí opakovat (takže ani hrany). Neobsahuje kružnice.

- $u = v$ - kružnice

> [!note] Kružnice
Uzavřené sledy, tahy, cesty tvoří kružnici.

### Dijkstraův algoritmus
![[Dijkstraův algoritmus]]

## Acyklický graf
Neobsahuje kružnici jako svůj podgraf. 
(les)

$G = (V,H)$
Na množině V definujeme relaci následovně:

u ~ v $\rightarrow$ existuje v G u-v cesta

Relace ekvivalence:
- reflexivní,
- symetrická,
- tranzitivní.

Třídy rozkladu V se nazývají komponenty grafu.

Komponenta je maximální co do počtu vrcholů souvislá část grafu.

> [!note] Graf se nazývá souvislý, jestliže má právě jednu komponentu grafu.

### Strom
![[Strom]]

### Les
![[Les]]
### Kostra grafu
![[Kostra grafu]]

### Kruskalův algoritmus

![[Kruskalův algoritmus]]

## Homeomorfismus grafů

Řekneme že grafy jsou homomorfní, jestliže existuje graf $G = (V,H)$ taková že $G_1$ i $G_2$ vzniknou z $G$ operacemi dělení hran.
## Isomorfismus grafů
Jsou vlastně stejné (třeba jinak pojmenované, nebo nakreslené).
Identické grafy.

$G_1 ~ G_2$ jsou isomorfní jestliže existuje zobrazení $f(v): V_1 \rightarrow V_2$, které je vzájemně jednoznačné, také že pro každé $u,v \in V_1$ platí, že:
$\{u,v\} \in H_1 <-> \{f(u),f(v)\} \in H_2$

## Rovinné grafy
Je takové graf, pro které existuje nakreslení v rovině bez křížení hran.

> [!tip] Kuratozli:
$G$ je rovinný právě tehdy, jestliže jako svůj podgraf neobsahuje graf homeomorfní s $K_{3,3}$ nebo $K_5$.