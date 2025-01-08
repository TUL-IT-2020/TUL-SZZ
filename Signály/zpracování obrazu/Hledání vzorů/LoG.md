# LoG

Aproximace operátoru LoG v masce (mexický klobouk) 5×5.

$$
\text{Maska} =
\begin{bmatrix}
0 & 0 & -1 & 0 & 0 \\
0 & -1 & -2 & -1 & 0 \\
-1 & -2 & 16 & -2 & -1 \\
0 & -1 & -2 & -1 & 0 \\
0 & 0 & -1 & 0 & 0
\end{bmatrix}
$$

Prahování LoG obrazu v intervalu hodnot blízkých k nule (slabé - nespojité hrany), lepší je použít detektor průchodů nulou, např. v masce 2 × 2 s reprezentativním bodem v levém horním rohu, Hrana se indikuje tehdy, pokud se uvnitř okna mění znaménko.