# Permutace
> [!tip] Permutace
Vzájemně jednoznačné zobrazení.

$$
\pi: A \rightarrow A
$$

Permutací $\pi$ na množině $X$ rozumíme vzájemně jednoznačné zobrazení z $X \rightarrow X$.   

Kde:
- $X = \{1,2,...,n\}$ ... množina 
- o $n$ prvcích
- $\pi, \rho$ ... permutace na $n$-prvkové množině $X$

> [!warning]
Násobení permutací není komutativní. 
Násobení disjunktních cyklů komutativní je.

## Zápis permutací
### Dvouřádkový zápis:
$$
\pi = 
\begin{pmatrix}
1 & 2 & 3 & 4 \\
3 & 1 & 4 & 2
\end{pmatrix}
$$

### Cyklus v permutaci:

> [!tip] Definice: Cyklus
> Permutaci $\pi \in S_n$ nazveme cyklem délky $k (1 \ge k \ge n)$, pokud existuje podmnožina $\{i_1, i_2, ..., i_k\} \subset \{1,2,...,n\}$ taková, že $\pi(i_1) = i_2, \pi(i_2) = i_3, ..., \pi(i_k) = i_1$ a pro všechny ostatní prvky $i \notin \{i_1,...,i_k\}$ platí $\pi(i) = i$.

$\pi =$ 
1 2 3 4 5 6 6 7
5 7 3 2 4 6 8 1

$\pi = (1 5 4 2 7 8)(3)(6)$

$\pi = (1 5 4 2 7 8)$

Cyklus je permutace, máme operaci násobení.
Cykly lze násobit.

$\pi * \rho =$
$(1, 5, 3, 2)*(3,4) = (1,5,4,3,2)$

$(3,4)*(1, 5, 3, 2) = (3,4,2,1,5) = (1,5,3,4,2)$


#### Cyklus délky 2 - Transpozice
Cyklus $(i_i, ..., i_k)$, $k \ge 2$ lze zapsat jako součin transpozic:

$$
(i_1, i_2, ..., i_k) = (i_1, i_2)(i_1, i_3)...(i_1, i_k)
$$

#### Inverzní cyklus

$$(i_1, i_2, ..., i_k)^{-1} = (i_k, i_{k-1}, ..., i_1)$$

$(1 5 4 3 2)^{-1} = (1 2 3 4 5)$

### Součin (disjunktních) cyklů
Každou permutaci lze napsat ve tvaru součinu disjunktních cyklů a to jednoznačně, pokud nepřihlížíme k jejich pořadí.

$$
cyc\_str(\pi) = x_1^{(\alpha_1)}*...*x_n^{(\alpha_n)}
$$

> [!tip] Součin disjunktních cyklů
Řekneme, že cykly $\pi, \rho \in S_n$, kde $\pi(i_1,...,i_k)$ a $\rho=(j_1,...,j_r)$ jsou disjunktní $\{i_1,...,i_k\} \cap \{j_1,...,j_r\} = \emptyset$.

## Sudé a liché permutace

Sečteme-li počet transpozic v rozkladu permutace na součin transpozic, dostaneme číslo, které je buďto sudé, nebo liché.

## Co na to grupy
- [[Grupy]]

- $(S_n, *)$ ... symetrická grupa
- $|S_n| = n!$ ... počet prvků
- $*$ ... skládání permutací

> [!note]
> Lze použít k popisu symetrie objektů.

> [!warning]
$$\pi \rho (i) = \rho (\pi (i))$$

## Množina všech permutací

> [!tip] Definice: Množina všech permutací
> Na množině ${1,...,n}$ vybavena operací násobení (skládání zobrazené) označujeme $(S_n, *)$ a nazýváme ji symetrická grupa na n-prvkové množině.

> Když matematik neví jak by něco dokázal, tak řekne že je to zřejmé.
> - Picek
## Generování permutací
![[Generovaní permutací v lexikografickém pořadí]]

## Příklady 

- [[Permutace příklad]]

## Příklad - násobení permutací
$\pi =$
1 2 3 4 5
4 3 2 4 1

$\rho =$
1 2 3 4 5
2 1 5 4 3

### Postup
$\pi \rho =$
1 2 3 4 5
4 5 1 3 2

$\rho \pi=$
1 2 3 4 5
3 4 1 5 2


## Příklad - cykly

$\pi =$
1 2 3 4 5 6 7 8 9 
9 5 2 6 7 4 3 1 8

### Řešení
(1 9 8)(2 5 7 3)(4 6)

## Příklad - cykly a transpozice
$\pi =$
(1 2 3 4)

### Řešení
(1 2)(1 3)(1 4)

