# Soustava rekurencí

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

- $a_1$ ... $a_m$ ... vlastní čísla matice A
- a sloupce matice V ... vlastní vektory

[[Vlastní čísla a vlastní vektory matic]]

řešení:

$$
x_n = \sum_{i =1}^m c_i \lambda_i^n v_i
$$

- $v_i$ příslušný vlastní vektor

