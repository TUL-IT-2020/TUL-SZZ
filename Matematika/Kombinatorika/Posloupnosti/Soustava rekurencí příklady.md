# Soustava rekurencí příklady
## Příklad
Bod v rovině se každým krokem otočí proti směru hodinových ručiček.

Počáteční pozice: $(1,0)$

Určete souřadnici po $n$ krocích.

```
pozice = {
(1,0)
(0,1)
(-1,0)
(0,-1)
}
```
### Postup
Rekurentně:
$x_{n+1} = -y_n$

$y_{n+1} = x_n$

Maticově:

$x_n = A^n x_0$
$$
A = \begin{pmatrix}
0 & -1 \\
1 & 0
\end{pmatrix}
$$

#### Vlastní čísla:
$$
\det \begin{pmatrix}
-\lambda & -1 \\
1 & -\lambda
\end{pmatrix}
$$

$$
-\lambda^2 + 1 = 0
$$

$$
\lambda_{1,2} = \pm i
$$

#### Vlastní vektory:

$(A - \lambda I)\mathbf{v} = \mathbf{0}$

Dosadíme vlastní čísla:

$\lambda_1 = -i$
$$
\left(
\begin{array}{cc|c}
-i & -1 & 0 \\
1 & -i & 0
\end{array}
\right)
$$

$-i x - y = 0$

Jednu zvolíme: 
$x = 1$

Druhou dopočítáme:
$y = -i$

$v_1 = \begin{pmatrix}1 \\ -i\end{pmatrix}$

$\lambda_1 = i$

$$
\left(
\begin{array}{cc|c}
i & -1 & 0 \\
1 & i & 0
\end{array}
\right)
$$

$i x - y = 0$

Jednu zvolíme: 
$x = 1$

Druhou dopočítáme:
$y = i$

$v_2 = \begin{pmatrix}1 \\ i\end{pmatrix}$

$$
x_n = c_1 i^n \begin{pmatrix}1 \\ -i\end{pmatrix}
+ c_2 (-i)^n \begin{pmatrix}1 \\ i\end{pmatrix}
$$

Dosadíme počáteční podmínky:
$$
\begin{pmatrix}1 \\ 0\end{pmatrix}
= c_1 \begin{pmatrix}1 \\ -i\end{pmatrix}
+ c_2 \begin{pmatrix}1 \\ i\end{pmatrix}
$$

Soustava rovnic:
$$
c_1 + c_2 = 1
$$
$$
-i c_1 + i c_2 = 0
$$
$$
c_1 = c_2 = \frac{1}{2}
$$

### Řešení
$$
x_n = \frac{1}{2} i^n \begin{pmatrix}1 \\ -i\end{pmatrix}
+ \frac{1}{2} (-i)^n \begin{pmatrix}1 \\ i\end{pmatrix}
$$

## Příklad
$x_{n+1} = 0.7x_n - 0.6 y_n$

$y_{n+1} = 0.6 x_n + 0.7 y_n$

Počáteční podmínky:
$x_0 = 1$
$y_0 = 0$

### Řešení
$\lambda_{1,2} = 0.7 \pm 0.6 i$

$r = \sqrt{0.7^2 + 0.6^2} = \sqrt{0.85} < 1$

$x_n = r^n \cos(n \theta)$

$y_n = r^n \sin(n \theta)$

> [!note]
> r < 1, tedy posloupnost konverguje k (0,0)

## Příklad: webové stránky

(*Markovské řetězce*, [[PageRank]])

Webová stránka má 3 podstránky:
- A - úvodní stránka,
- B - články,
- C - e-shop.

Statistické údaje:
- A -> A(0.2%), B (0.6%), C (0.2%),
- B -> A(0.3%), B (0.2%), C (0.5%),
- C -> A(0.4%), B (0.1%), C (0.5%).

Matice přechodu:
$$
P = \begin{pmatrix}
0.2 & 0.3 & 0.4 \\
0.6 & 0.2 & 0.1 \\
0.2 & 0.5 & 0.5
\end{pmatrix}
$$

$x_n = P^n x_0$

Hledá se rovnovážný stav:
$$
P x^* = x^*
$$

$$
(x_1^*, x_2^*, x_3^*) = 1
$$

## Příklad: model šíření viru

- $S_n$ - počet zdravých v čase $n$,
- $I_n$ - počet infikovaných v čase $n$,
- $R_n$ - počet vyléčených v čase $n$.

Model:
$$
S_{n+1} = S_n - \beta S_n I_n
$$
$$
I_{n+1} = I_n + \beta S_n I_n - \gamma I_n
$$
$$
R_{n+1} = R_n + \gamma I_n
$$