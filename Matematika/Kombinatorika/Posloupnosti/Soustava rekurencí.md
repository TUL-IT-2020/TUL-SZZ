# Soustava rekurencí

> [!note]
> Možné řešení [[PageRank]] algoritmu přes vlastní čísla místo iterativního přístupu.


$x_n \in R^n$

$$
x_{n+1} = A x_n
$$

Kde:
- $A$ je matice $m*m$
- $x$ je vektor o $m$ prvcích
$$
x_n =
\begin{pmatrix}
x_n^1 \\
... \\
x_m
\end{pmatrix}
$$
Pokud počáteční podmínky reprezentuje $x_0$, pak řešení HLR:
$$
x_n = A^n x_0
$$
## Řešení:

$x_n = A^n x_0$

$A = V \Lambda V^{-1}$

$$
\Lambda =
\begin{pmatrix}
\lambda_1 & ... & 0 \\
0 & ... & 0 \\
0 & ... & \lambda_m
\end{pmatrix}
$$

- $\lambda_1$ ... $\lambda_m$ ... vlastní čísla matice A
- a sloupce matice V ... vlastní vektory

[[Vlastní čísla a vlastní vektory matic]]

řešení:

$$
x_n = \sum_{i =1}^m c_i \lambda_i^n v_i
$$

- $v_i$ příslušný vlastní vektor


### Různé kořeny
Kořeny charakteristického polynomu jsou různé.
Matice A lze přepsat do tvaru:
$$
A = V \Lambda V^{-1}
$$
Vlastní čísla jsou různá:
$\lambda_1 \neq \lambda_2 ... \neq \lambda_m$

V ... obsahuje vlastní vektory k vlastním číslům $\lambda_i$.

$$
A^n = (V \Lambda V^{-1})^n
$$
$$
(V \Lambda V^{-1} V \Lambda V^{-1}) ... = V \Lambda^n V^{-1} 
$$
- $V^{-1} V$ ... se požerou

Co se stane v matici? Má prvky jen na diagonále?
$$
\Lambda^n =
\begin{pmatrix}
\lambda_1^n & ... & 0 \\
0 & ... & 0 \\
0 & ... & \lambda_m^n
\end{pmatrix}
$$

> [!question]
> $x_{libo}$ ... má vztah k vlastním vektorům? 

Lineární kombinace s vlastním vektorem.
$$
x_{libo} = c_1v_i + c_2v_2+...+c_mv_m
$$
- $v$ ... vlastní vektor

řešení:
$$
x_n = \sum_{i=1}^m c_i v_i \lambda_i^n
$$

Hodnoty $c_i$ určíme z počátečních podmínek.

## Příklad

### Králíci zjednodušený model

- $u_n$ ... počet mláďat
- $d_n$ ... počet dospělých v čase $n$

$u_{n+1} = d_n + 0$
$d_{n+1} = d_n + u_n$

Za každého dospělého jedno mládě. 
Mladí dospějí (ale nikdo neumírá).

$$
x_n = \begin{pmatrix}
u_n \\
d_n
\end{pmatrix}
$$
#### Vlastní čísla:
$det(A-\lambda I)$

$$
\det \begin{pmatrix}
0-\lambda & 1 \\
1 & 1-\lambda
\end{pmatrix}
$$

$\lambda =\frac{1\pm \sqrt(5)}{2}$

#### Vlastní vektory:
$A = V \Lambda V^{-1}$

$A v =  \lambda v$
$(A - \lambda I)\mathbf{v} = \mathbf{0}$

$\varphi = \lambda_1$
$\psi = \lambda_2$
$$
\left(
\begin{array}{cc|c}
-\varphi & 1 & 0 \\
1 & 1 - \varphi & 0
\end{array}
\right)

\sim

\left(
\begin{array}{cc|c}
-1 & 1/\varphi & 0 \\
0 & 1 - \varphi + 1/\varphi & 0
\end{array}
\right)
$$
1r $/ \varphi$
2r+1r

Použijeme vztah z charakteristického polynomu:

$\frac{1}{\varphi}=\varphi-1$

Takže

$$
1-\varphi+\frac{1}{\varphi}=1-\varphi+(\varphi-1)=0
$$
Druhá řada je tedy nulová, dostaneme jediný nezávislý rovinný vztah z prvního řádku:

$$
-1\cdot x + \frac{1}{\varphi} y = 0 \quad\Longrightarrow\quad y=\varphi x
$$

Můžeš vzít vlastní vektor (pro $\varphi$)

$$
\mathbf v_1=\begin{pmatrix}1\\[4pt]\varphi\end{pmatrix}
$$

Analogicky pro druhé vlastní číslo $\psi$ dostaneš

$$
\mathbf v_2=\begin{pmatrix}1\\[4pt]\psi\end{pmatrix}
$$

#### S počátečními podmínkami:
$$
x_n = c_1 v_1 + c_2 v_2
$$

$$
x_0 = 
\begin{pmatrix}
0\\
1
\end{pmatrix}
$$

$$
\begin{pmatrix}
0\\
1
\end{pmatrix}
=
c_1 \begin{pmatrix}1\\ \varphi\end{pmatrix} + c_2 \begin{pmatrix}1\\ \psi\end{pmatrix}
$$

$0 = c_1 + c_2$
$1 = c_1 \varphi + c_2 \psi$

$- c_1 = c_2$
$1 = c_1 \varphi - c_1 \psi$

$$
c_2 
= \frac{1}{\varphi-\psi} 
= \frac{\sqrt(5)}{5}
$$

$$
c_2 
= -\frac{1}{\varphi-\psi} 
= \frac{-\sqrt(5)}{5}
$$
#### Obecné řešení
$$
x_n = \frac{\sqrt(5)}{5} \varphi^n \begin{pmatrix}1\\ \varphi\end{pmatrix}
- \frac{\sqrt(5)}{5} \psi^n \begin{pmatrix}1\\ \psi\end{pmatrix}
$$

