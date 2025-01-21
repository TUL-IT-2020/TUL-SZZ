# Permutace
- [[Permutace]]
- [[Generovaní permutací v lexikografickém pořadí]]
## Bez opakování
n různých prvků.

Permutace řádu n je uspořádaná [[Entice|entice]].

> [!tip] Počet permutací:
$$
P(n) = A^n_n = n!
$$

Kde:
- $P(n)$ - počet permutací řádu n bez opakování na n prvkové množině.
- $n \in N$

Platí:
$P(n) = n P(n-1)$
- $P(0) = 1$

$P(n) = (n-1)(P(n-1) + P(n-2))$

## Permutace s opakováním
Celkem n prvků mezi nimi:
- $n_1$ - prvky stejného 1. druhu (nerozlišitelné)
- $n_2$ - prvky stejného 2. druhu
- ...
- $n_k$ - prvky stejného k. druhu

$$
\{a_1,...a_1,a_2,...,a_2,...,a_k,...,a_k\}
$$
- $n_1*a_1$

> [!tip] Počet permutací s opakováním
$$
P(n_1, ..., n_k) = \frac
{(n_1+...+n_k)!}
{n_1! * n_2! * ...* n_k!}
$$

> [!question] Proč?
Počet všech kombinací písmen musíme zmenšit o počet prohození identických písmen.

## Příklady
- [[Permutace počet příklady]]