# Barvení objektu

> [!tip] Obarvení n prvkového objektu pomocí m zadaných barev
K obarvení kteréhokoliv prvku objektu lze využít kteroukoliv z $m$ zadaných barev. A to bez ohledu na obarvení ostatních prvků objektu.

> [!question]
> Kolika způsoby lze obarvit všechny vrcholy čtverce 2 barvami?

Nakresli si:
- Všechny bílé
- Jeden černý
- Dvě černé
- 3 černé
- Všechny černé

B-B
 |  |
B-B

$2^4 = 16$ ... obarvení, ale co na to symetrie?

Všechny symetrické obarvení považujeme za stejné:
- 6 ... různých obarvení.
## Stejná obarvení

> [!tip] Stejná obarvení
Obarvení jsou stejná, jestliže existuje permutace $\pi \in P$ taková, že $b_i^{(1)} = b_{\pi(1)}^{(2)}$.

$$
\exists \pi \in P; \forall i \in  \{1,...,n\}; b_i^2=b_{\pi(i)}^1  
$$
$G=(X,P)$
Obarvení $x$:
- $(b_1^1,....,b_n^1)$
- $(b_1^2,...,b_n^2)$

$$
P_G(x_1, .., x_n) = \frac{1}{|P|} \sum_{\pi \in P} cyc\_str(\pi)
$$
## Počet různých obarvení
> [!tip] Pólyova věta: Počet různých obarvení objektu
Nechť $X= {1,2,...,n}$ je množina reprezentující $n$ prvkový objekt, jehož symetrie jsou definovány permutační grupou $G=(X,P)$ a $P_G(x_1,...,x_n)$ je její cycle-index polynom. Potom počet různých obarvení objektu pomocí $m$ zadaných barev je roven počet $P_G(m,...m)$. Tedy v hodnotě cycle-index polynomu v bodech:
>- $x_1=m$
>- ...
>- $x_n = m$

> [!note]
> Prostě dosadíme za $x$ polynomu cyklické struktury. 

## Barvíme čtverec

| m        | 2   | 3   | 4   | ... | 100 |
| -------- | --- | --- | --- | --- | --- |
| $P_{2D}$ | 6   | 24  | 70  |     |     |
| $P_{3D}$ | 6   | 21  | 55  |     |     |
> [!note]
> Počet obarvení ve 3D bývá stejný nebo menší než ve 2D.  

## Jak to spočítat?
$$
P_G(x_1, .., x_n) = \frac{1}{|P|} \sum_{\pi \in P} cyc\_str(\pi)
$$
- $X=\{1,...,n\}$
- $G=(X,P)$
- $c_1, ..., c_k$ - k různých barev

### 2 barvy čtverec ve 2D:
Polynom cyklického indexu:
$$
P_{2D}(x_1,x_2,x_3,x_4) = \frac{1}{4}(x_1^4 + x_2^2 + 2x_4)
$$
$$
\frac{1}{4}(2^4 + 2^2 + 2*2) = \frac{1}{4}(16 + 4 + 4) = \frac{24}{4} = 6
$$
### 2 barvy čtverec ve 3D:
Polynom cyklického indexu:
$$
P_{3D}(x_1,x_2,x_3,x_4) = \frac{1}{8}(x_1^4 + 2x_1^2x_2 + 3x_2^2 + 2x_4)
$$

$$
\frac{1}{8}(x^4 + 2x^2 x + 3x^2 + 2x) = \frac{1}{8}(16 + 2*2^2*2 + 3*4 + 4) = \frac{48}{8} = 6
$$

### 3 barvy čtverec ve 2D:
24
### 3 barvy čtverec ve 3D:

Polynom cyklického indexu:
$$
P_{3D}(x_1,x_2,x_3,x_4) = \frac{1}{8}(x_1^4 + 2x_1^2x_2 + 3x_2^2 + 2x_4)
$$

$$
\frac{1}{8}(3^4 + 2*3^2*3 + 3*3^2 + 2*3) = \frac{192}{8} = 21
$$

## Kolik existuje takových obarvení že: 
> [!question] 
> Kolik existuje takových obarvení že:
>- $c_1$ použiji právě $n_1$ - krát,
>- ...
>- $c_k$ použiji právě $n_k$ - krát

Tedy:
$n_1 *  c_1, ... , n_k * c_k$

> [!tip] Věta pro pevné použití barev
Nechť $X=\{1,...,n\}$ je množina reprezentující n-prvkový objekt a $P_G(x_1,...,x_n)$ je cycle index polynom grupy symetrií daného objektu. Potom počet obarvení daného objektu pomocí k barev $c_1,...,c_k$, kde $c_1$ použiji $n_1$ krát, ..., $c_k$ použiji $n_k$ krát $(\sum_{i=1}^k n_i = n)$ je roven koeficientu u členu: $c_1^{n_1},...,c_k^{n_k}$ v rozvoji:
$$
P\left(
\sum_{i=1}^k c_i,
\sum_{i=1}^k c_i^2,
...,
\sum_{i=1}^k c_i^n,
\right)
$$

$$
\sum_{i=1}^k n_i = n
$$
$$
P_G(x_1,...,x_n)|x_i = \hat b_1 + \hat b_2 + ... + \hat b_n
$$
