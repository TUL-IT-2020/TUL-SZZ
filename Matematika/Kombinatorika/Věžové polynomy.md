# Věžové polynomy
> [!tip] Šachovnice
Šachovnicí typu (m,n), $m x n$, kde $m, n \in N^+$ rozumíme obdélníkové schéma obsahující $m*n$ čtvercových polí uspořádaných do m řad (horizontál) a n sloupců (vertikál).
Některá pole šachovnice mohou být tzv zakázaná, ostatní označujeme jako přípustná (povolená pole).

Na zakázaná pole nelze umístit věž.

Věže považujeme za nerozlišitelné.

- $c, c_1,...$ značení šachovnic

> [!note] Podšachovnice
Obdélníková podmnožina šachovnice.

> [!question] Otázka:
Kolika různými způsoby lze na zadanou šachovnici C rozmístit k nerozlišitelných věží tak že stojí na přípustných polích a vzájemně se neohrožují?

Dvě věže se ohrožují, když stojí ve stejném řádku nebo sloupci.

Věže se neohrožují, když každá z věží stojí v jiném řádku a jiném sloupci.

$r_k (C)$ ... kolika způsoby lze na šachovnici $C$ rozmístit $k$ věží.

Věžový polynom šachovnice c je (obyčejná) vytvořující funkce posloupnosti $\{r_k(C)\}_{k=0}^\infty$, $\{r_k(C)\}_{k=0}^{min(m,n)}$
Značení: 
$$
r(x_i, C) = r_0(c) + r_1(c)x + r_2 (c)x^2 ... = \sum_{k=0}^{min(m,n)} r_k(c)x^k
$$
- $r$ ... anglicky věž
- $min(m,n)$ ... maximum věží na šachovnici 

Věžový polynom je invariantní vzhledem k záměně řádků či sloupců.

## Úlohy s věžovými polynomy
[[Úlohy s věžovými polynomy]]