# Úvod do teorie grafů

Grafein - z latinského psát
$$\gama \rho \alpha \varphi \epsilon \i \v$$
## Neorientovaný graf
![[Neorientovaný graf]]

## Orientovaný graf
![[Orientovaný graf]]
## Hrany a vrcholy
$$
h = \{v_i, v_j\}
$$
Hrana a vrcholy v_i a v_j jsou incidentní (tvoří hranu).
v_i a v_j jsou sousední vrcholy.


### Smyčka

Hrana, která vede ze stejného vrcholu zpátky do něj.
### Paralelní hrany
$h_i = \{v_i, v_j\}$
$h_j = \{v_i, v_j\}$

$i \neq j$

Hrany, které spojují stejné vrcholy

## Dělení grafů
### Jednoduchý graf
Graf, který neobsahuje paralelní hrany ani smyčky. 

### Multigraf
Graf který neobsahuje smyčka. Může obsahovat paralelní hrany.  

## Síť
Hranově ohodnocená síť.
$$
G = (V,H,c)
$$

- c : H -> R^+ (R)
Ohodnocení (kapacita) hran.

## Kružnice

$C_n$ - kružnice na $n$ vrcholech
- $n \in N^+$

## Úplný graf na N vrcholech
$K_n$
- $n \in N^+$

K_5 - nejmenší graf, který není rovinný

## Bipartitní graf

$$
G = (V_1 u V_2 , H)
$$

$V_1 a V_2 = \empty$
$\forall h \in H$
$h a V_1 \ne \empty \; a \; h a V_1 \ne \empty$

$|H(K_n)| = C^2_n = \frac{n(k-1)}{2}$

### úplný bipartitní graf

$K_{m,n}$ - úplný bipartitní graf na $m,n$ vrcholech
- $m,n \in N^+$


$K_{3,3} = K_5$

## Kolo
$W_n$
- $n = N^+$

"Kolo s osou":
- Kružnice na $n-1$ vrcholech,
- Přidáme jeden vrchol a propojíme ho s každým vrcholem.

## Zadávání grafů

1) Výčet vrcholů a výčet hran,
2) Matice sousednosti,
3) Matice incidence,
4) Spojové seznamy,
5) Nakreslení grafu.

### Matice sousednosti
$$
A = (a_{ij})^{|V|}_{i,j = 1}
$$

- $A$ - matice VxV.
- $a_{ij}$ - má hodnotu počtu hran spojujících daní vrcholy (i,j), běžně má hodnotu jedna.

Diagonála - určuje zda máme smyčky
Symetrická - pokud není graf orientovaný

### Matice incidence
$$
M = (m_{ij})^{|V|,|H|}_{i,j = 1}
$$

Obdélníková matice

$m_{ij}$:
- $1$ - $v_i \in k_j$
- $0$ jinak

### Spojové seznamy
Každý vrchol má seznam svých sousedních vrcholů.


