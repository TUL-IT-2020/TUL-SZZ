# Řešení soustav rekurentních vztahů metodou vytvořujících funkcí
$$
a_n = \alpha_{11} a_{n-1} + \alpha_{12} b_{n-1} + ... + u_n
$$

$$
b_n = \alpha_{21} a_{n-1} + \alpha_{22} b_{n-1} + ... + v_n
$$

S počátečními podmínkami.
- $a_0, b_0$

$$
A(x) = \sum_{n=0}^{\infty} a_n x^n
$$

$$
B(x) = \sum_{n=0}^{\infty} b_n x^n
$$

## Maticově

[[Soustava rekurencí]]

$$
\vec{a_n} = M \vec{a_{n-1}}
$$

$$
A(x) = \sum_{n=0}^{\infty} \vec{a_n} x^n
$$ 

$$
(I - xM) A(x) = \vec{a_0}
$$

Vytvořující funkce:
$$
A(x) = (I - xM)^{-1} \vec{a_0}
$$

## Příklad
$a_n = b_{n-1}$

$b_n = a_{n-1} + b_{n-1}$

$n \geq 1$

- $a_0 = 0$
- $b_0 = 1$

### Postup:

#### Přenásobit $x^n$ a sečíst od $n=1$ do $\infty$:

$$
\sum_{n=1}^{\infty} a_n x^n = \sum_{n=1}^{\infty} b_{n-1} x^n
$$

$$
\sum_{n=1}^{\infty} b_n x^n = \sum_{n=1}^{\infty} a_{n-1} x^n + \sum_{n=1}^{\infty} b_{n-1} x^n
$$

#### A(x) a B(x)

$$
A(x) - a_0 = x B(x)
$$

$$
B(x) - b_0 = x A(x) + x B(x)
$$

#### Dosadíme počáteční podmínky:

$$
A(x) - 0 = x B(x)
$$

$$
B(x) - 1 = x A(x) + x B(x)
$$

#### Vyjádříme A(x) a B(x):

$$
B(x) - 1 = x^2 B(x) + x B(x)
$$

$$
B(x) (1 - x - x^2) = 1
$$

$$
B(x) = \frac{1}{1 - x - x^2}
$$

$$
A(x) = x B(x) = \frac{x}{1 - x - x^2}
$$

...

$$
B(x) = \sum_{n=0}^{\infty} b_{n} x^{n+1}
$$

$$
A(x) = \sum_{n=0}^{\infty} a_{n} x^{n}
$$

### Řešení

(už jmse někdy řešily)

## Příklad

$$
a_n = 2 a_{n-1} - b_{n-1} +1
$$

$$
b_n = a_{n-1} + b_{n-1}
$$

$n \geq 1$

$|x| < 1$

- $a_0 = 0$
- $b_0 = 0$

### Postup:

1.

$$
\sum_{n=1}^{\infty} a_n x^n = 
2 \sum_{n=1}^{\infty} a_{n-1} x^n  + 
\sum_{n=1}^{\infty} b_{n-1} x^n + \sum_{n=1}^{\infty} x^n 
$$

2.
$$
\sum_{n=1}^{\infty} b_n x^n = \sum_{n=1}^{\infty} a_{n-1} x^n + \sum_{n=1}^{\infty} b_{n-1} x^n
$$

#### A(x) a B(x)

$$
A(x) = 2xA(x) - xB(x) + \frac{x}{1-x}
$$

> [!note]
$$
\sum_{n=0}^{\infty} x^n = \frac{1}{1-x}
$$

$$
B(x) = xA(x) + xB(x)
$$

#### Vyjádříme A(x) a B(x):
$$
B(x) - xB(x) = xA(x)
$$

$$
B(x) (1-x) = xA(x)
$$

$$
A(x) = \frac{(1-x)}{x} B(x)
$$

$$
B(x) = \frac{x}{1-x} A(x)
$$

#### Dosadíme do první rovnice:

$$
A(x) = \frac{x}{(1-3x+3x^2)}
$$
(tohle nám stačí)

...
$$
A(x) = 2xA(x) - \frac{x^2}{1-x} A(x) + \frac{x}{1-x}
$$

$$
A(x) = \frac{2xA(x) -2x^2A(x) - x^2 A(x) + x}{1-x}
$$

Parciální zlomky:

## Příklad

$$
a_{n} = 3 a_{n-1} + 2 b_{n-1}
$$

$$
b_{n} = a_{n-1} + b_{n-1}
$$

Počáteční podmínky:
- $a_0 = 2$
- $b_0 = 1$

Maticově:
$$
M = \begin{pmatrix}
3 & 2 \\
1 & 1
\end{pmatrix}
$$

$$
\vec{a_0} = \begin{pmatrix}
2 \\
1
\end{pmatrix}
$$

$$
A(x) = \begin{pmatrix}
    A(x) \\
    B(x)
\end{pmatrix}
$$
### Postup:
Vytvořující funkce:
$$
A(x) = (I - xM)^{-1} \vec{a_0}
$$

$$
I - xM = \begin{pmatrix}
1-3x & -2x \\
 -x & 1 - x
\end{pmatrix}
$$

Inverze přes determinant:

$$
det(I - xM) = (1-3x)(1-x) - 2x^2 = 1 -4x + x^2
$$

Algebraický doplněk:
$$
(I - xM)^{-1} = \frac{1}{det(I - xM)} (I - xM)^{adj}
$$
[[7. Determinant.pdf]]

$$
(I - xM)^{-1} = \frac{1}{1 -4x + x^2} \begin{pmatrix}
1 - x & 2x \\
x & 1 - 3x
\end{pmatrix}
$$

$$
(I - xM)^{-1} = \frac{1}{1 -4x + x^2} \begin{pmatrix}
1 - x & 2x \\
x & 1 - 3x
\end{pmatrix}
\begin{pmatrix}
2 \\
1
\end{pmatrix}
$$

### Po nějakých úpravách:

$$
A(x) = \begin{pmatrix}
\frac{2}{1 - 4x + x^2} \\
\frac{1-x}{1 - 4x + x^2}
\end{pmatrix}
$$