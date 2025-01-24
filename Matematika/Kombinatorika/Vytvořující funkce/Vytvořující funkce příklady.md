# Vytvořující funkce

## Příklad
$$
a_{n+2} - a_{n+1} - 2a_n = (-1)^n
$$

- $a_0 = 1$
- $a_1 = 1$

### Postup
$$
\{a_n\}_{n=0}^\infty ... f(x) = \sum_{n=0}^\infty a_n x^n
$$

Přenásobíme $x^{n+2}$
$$
a_{n+2}x^{n+2} - a_{n+1}x^{n+1} - 2x^2a_n x^{n} = x^2*(-1)^n
$$

$$
\sum_{n=0}^\infty a_{n+2}x^{n+2} 
- x\sum_{n=0}^\infty a_{n+1}x^{n+1} 
- 2x^2\sum_{n=0}^\infty a_n x^{n} 
= \frac{x^2}{1+x} x^{2} \sum_{n=0}^\infty (-x)^n 
$$

- $f(x) - a_0 - a_1x$
- $f(x) -a_0$
- $f(x)$

$$
f(x) - 1 - x -x(f(x)-1) - 2x^2f(x) = \frac{x^2}{1+x}
$$

Uzavřený tvar:
$$
f(x) = \frac{x^2+x+1}{(1+x)(1-x-2x^2)}
$$

Rozklad na parciální zlomky:

$(1-x-2x^2) = (1+x)(1-2x)$

$$
f(x) = \frac{A}{(1+x)^2} + \frac{B}{1+x} + \frac{C}{1-2x}
$$
Proč?

Dopočítat $A, B, C$ a dosadit do $f(x)$.

### Řešení
$$
f(x) = \frac{1}{3} \cdot \frac{1}{(1+x)^2} 
- \frac{1}{9} \cdot \frac{1}{1+x} 
+ \frac{7}{9} \cdot \frac{1}{1-2x}
$$

## Metodou vytvořujících funkcí vyřešte rekurentní vztah

$$
a_{n+1} = -2a_n -4b_n
$$
$$
b_{n+1} = 4a_n + 6b_n
$$

- $a_0 = 1$
- $b_0 = -2$

### Postup

- $\{a_n\}_{n=0}^\infty ... f(x)$
- $\{b_n\}_{n=0}^\infty ... g(x)$

1. Naleznětě uzavřený tvar pro $f(x)$ a $g(x)$,
2. Nalezněte rozvinuté tvary pro $f(x)$ a $g(x)$.

$$
f(x) -1+2xf(x)+4xg(x) = 0
$$
$$
-4xf(x) + g(x)+2 -6xg(x) = -2
$$

Upraveno:
$$
f(x)(1+2x) + 4xg(x) = 1
$$
$$
-4xf(x) + g(x)(1-6x) = -2
$$

GEM:
$$
\begin{pmatrix}
1 + 2x & 4x & 1 \\
-4x & 1-6x & -2 \\
\end{pmatrix}
$$

Kramerovo pravidlo, Sarrusovo pravidlo:
$$
f(x) = \frac{det(Af)}{det(A)}
$$

$$
g(x) = \frac{det(Ag)}{det(A)}
$$

$$
Af = \begin{pmatrix}
1 & 4x \\
-2 & 1-6x \\
\end{pmatrix}
$$

$$
Ag = \begin{pmatrix}
1+2x & 1 \\
-4x & -2 \\
\end{pmatrix}
$$

$$
A = \begin{pmatrix}
1+2x & 4x \\
-4x & 1-6x \\
\end{pmatrix}
$$

- $det Af = (1-6x) - (-8x) = 1-6x+8x = 1+2x$
- $det Ag = -2-4x-(-4x) = -2$
- $det A = 4x^2-4x+1$

Uzavřený tvar:
$$
f(x) = \frac{1+2x}{1-4x+4x^2}
$$

$$
g(x) = \frac{-2}{1-4x+4x^2}
$$

Rozklad na parciální zlomky:
$$
1-4x+4x^2 = (1-2x)^2
$$

$$
g(x) = \frac{-2}{(1-2x)^2}
$$

$$
f(x) = \frac{1+2x}{(1-2x)^2} 
= \frac{A}{(1-2x)} + \frac{B}{(1-2x)^2} 
= \frac{2}{(1-2x)} - \frac{1}{(1-2x)^2}
$$

- $A(1-2x) + B = 1+2x$, $A+B = 1$
- $A-2xA+B = 1+2x$, $A=2$

$$
1+qx+q^2x^2+q^3x^3+...+q^nx^n= \frac{1}{1-qx}
$$
$$
qx+q^2x^2+q^3x^3+...+q^nx^n= \frac{q}{(1-qx)^2}
$$

$$
(n+1)^{n+1}-2
$$
### Řešení
$$
a_n = 2^n(2n+1)
$$
$$
b_n = -(n+1)2^{n+2n}
$$

## Příklad
- $f(x)$ ... vytvořující funkce pro posloupnost $a_n$
- $g(x)$ ... vytvořující funkce pro posloupnost $b_n$

Vyjádřete $g(x)$ pomocí $f(x)$.
### Postup
- $b_3 = 3$
- $b_n = a_n$ pro $n \neq 3$
### Řešení
$$
g(x) = f(x) - a_3x^3 + 3x^3 = f(x) - 3x^3
$$
### Postup
- $b_1 = 1$
- $b_2 = 2$
- $b_n = 2a_n$ pro $n \neq 1,3$
### Řešení
$$
g(x) = 2f(x) + x(1-2a_1) + x^3(3-2a_3)
$$
### Postup
- $b_1 = 1$
- $b_2 = 2a_n+5$ pro $n \neq 1$

$a_n = n$ ... $f(x) = \frac{x}{(1-x)^2}$

$a_n = n^2$ ... $f(x) = \frac{x}{(1-x)^3}$

### Řešení
$$
g(x) = 2f(x)+\frac{5}{1-x} + x(1-5-2a_1)
$$

## Příklad
$$
f(x) = e^{qx}
$$

- $a_n = \frac{q^n}{n!}$ ... obyčejná vytvořující funkce
- $a_n = q^n$ ... exponenciální vytvořující funkce

![[Taylorův polynom]]

Derivace:
- $(e^{qx})' = qe^{qx}$
- $(e^{qx})'' = q^2e^{qx}$

## Příklad
$$
f(x) = -ln(1-x)
$$

$f(x) -ln(1-x)$ ... $a_n = -1^n*\frac{(n-1)!}{x^n}$

- $a_0 = 0$
- $a_1 = 1$
- $a_2 = 1/2$

### Postup
- $f'(x) = \frac{1}{1-x} = (1-x)^{-1}$
- $f''(x) = \frac{1}{(1-x)^2}$

- $a_n = 1/n$