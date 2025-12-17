# Zadávání grafů

1) Výčet vrcholů a výčet hran,
2) Matice sousednosti,
3) Matice incidence,
4) Spojové seznamy,
5) Nakreslení grafu.

## Matice sousednosti
![[Matice sousednosti]]

## Matice incidence
![[Matice incidence]]

## Spojové seznamy
Každý vrchol má seznam svých sousedních vrcholů.


## Příklady:

### Výčet vrcholů a hran:
Vrcholy:
V = {1,2,3,4}

Hrany:
H = {(1,2),(2,3),(3,4),(4,1)}

### Graficky:
1 - 2
  X 
3 - 4

### Matice sousednosti:
$$
A = \begin{pmatrix}
0 & 1 & 0 & 1 \\
1 & 0 & 1 & 0 \\
0 & 1 & 0 & 1 \\
1 & 0 & 1 & 0
\end{pmatrix}
$$

### Matice incidence:
$$
B = \begin{pmatrix}
1 & 0 & 0 & 1 \\
1 & 1 & 0 & 0 \\
0 & 1 & 1 & 0 \\
0 & 0 & 1 & 1
\end{pmatrix}
$$
Sloupce hrany, řádky vrcholy (tvořící danou hranu).

### Spojové seznamy:
- 1: 2,4
- 2: 1,3
- 3: 2,4
- 4: 1,3

