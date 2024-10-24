# Barvení objektu

> [!tip] Obarvení n prvkového objektu pomocí m zadaných barev
K obarvení kteréhokoliv prvku objektu lze využít kteroukoliv z m zadaných barev. A to bez ohledu na obarvení ostatních prvků objektu.

> [!question]
> Kolika způsoby lze obarvit všechny vrcholy čtverce 2 barvami?

Nakresli si:
- Všechny bílé
- Jeden černý
- Dvě černé
- 3 černé
- Všechny černé

$2^4 = 16$ ... obarvené, ale co na to symetrie?

Všechny symetrické obarvení považujeme za stejné:

6 ... různých obarvení.

> [!tip] Počet různých obarvení objektu
Nechť $X= {1,2,...,n}$ je množina reprezentující n prvkocý ojekt, jehož symetrie jsou dinovány permutační grupou $G=(X,P)$ a $P_G(x_1,...,x_n)$ je její cycle-index polynom. Potom počet různých obarvení objeketu pomocí m zadaných barev je roven počet $P_G(m,...m)$. Tedy v hodnotě cycle-index polynomu v bodech:
- $x_1=m$
- ...
- $x_n = m$

## Barvíme čtverec

| m        | 2   | 3   | 4   | ... | 100 |
| -------- | --- | --- | --- | --- | --- |
| $P_{2D}$ | 6   | 24  | 70  |     |     |
| $P_{3D}$ | 6   | 21  | 55  |     |     |
> [!note]
> Počet obarvení ve 3D bývá stejný nebo menší než ve 2D.  

> [!tip] Stejná obarvení

$G=(X,P)$
Obarvení x:
- $(b_1^1,....,b_n^1)$
- $(b_1^2,...,b_n^2)$

Obě uvedená obarvení jsou stejná, jestliže existuje:
$$
\exist \pi \in P; \forall i \in  \{1,...,n\}; b_i^2=b_{\pi(i)}^1  
$$

$$
P_G(x_1, .., x_n) = \frac{1}{|P|} \sum_{\pi \in P} cyc\_str(\pi)
$$

## Jak to spočítat

- $X=\{1,...,n\}$
- $G=(X,P)$
- $c_1, ..., c_k$ - k různých barev

Kolik existuje takových obarvení že: 
- $c_1$ použiji právě $n_1$ - krát,
- ...
- $c_k$ použiji právě $n_k$ - krát

$n_1 *  c_1, ... , n_k * c_k$

$$
\sum_{i=1}^k n_i = n
$$

Nechť $X=\{1,...,n\}$ je množina reprezentující n-prvkový objekt a $P_G(x_1,...,x_n)$ je cycle index polynom grupy symetrií daného objektu.
Potom počet obarvení daného objektu pomocí k barev $c_1,...,c_k$, kde $c_1$ použiji $n_1$ krát, ..., $c_k$ použiji $n_k$ krát $(\sum_{i=1}^k n_i = n)$ je roven koeficientu u členu: $c_1^{n_1},...,c_k^{n_k}$ v rozvoji:
$$
P\left(
\sum_{i=1}^k c_i,
\sum_{i=1}^k c_i^2,
...,
\sum_{i=1}^k c_i^n,
\right)
$$
