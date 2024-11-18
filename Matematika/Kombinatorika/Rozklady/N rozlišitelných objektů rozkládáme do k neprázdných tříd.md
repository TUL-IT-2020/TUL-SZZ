# N rozlišitelných objektů rozkládáme do k neprázdných tříd

$\{n nad k\}$ = počet rozkladů n prvkové množiny do $\{a_1,...,a_n\}$ do k neprázdných tříd

Stirling subset number řádu n,k.
$\left\{\begin{array}{c} 0 \\ 0 \end{array}\right\} = 1$
$\left\{\begin{array}{c} n \\ 0 \end{array}\right\} = 0$, $n \in N^+$
$\{n 1\} = 1$
$\{n 2\} = 2^{n-1}-1$, $n \geq 2$

$\left\{\begin{array}{c} n \\ n-1 \end{array}\right\} = C^2_n = \frac{n(n-1)}{2}$ 
$\left\{\begin{array}{c} n \\ n \end{array}\right\} = 1$



$$
\left\{\begin{array}{c} n \\ k \end{array}\right\} =
\left\{\begin{array}{c} n-1 \\ k-1 \end{array}\right\} +
k * \left\{\begin{array}{c} n-1 \\ k \end{array}\right\}
$$

Vybíráme prvek $a_1$ :
- tvoří samostatnou třídu $\left\{\begin{array}{c} n-1 \\ k-1 \end{array}\right\}$
- netvoří samostatnou třídu

#TODO: stirlingův trojuhelník

