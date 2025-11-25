# Vytvořující funkce

## Fibonnaciho posloupnost
$$
a_n = a_{n-1} + a_{n-2} 
$$
- $a_0 = 0$
- $a_1 = 1$

Hledáme pro: $n \ge 2$

### Postup:
Zapiš vytvořujícíc funkci
$$
A(x) = \sum_{n=0}^{\infty} a_n x^n
$$

#### Násobíme $x^n$ a sumuji.
$$
\sum_{n=2}^{\infty} a_n x^n = \sum_{n=2}^{\infty} a_{n-1}x^n + \sum_{n=2}^{\infty} a_{n-2} x^n
$$

> [!note]
$$
\sum_{n=2}^{\infty} a_n x^n = \sum_{n=0}^{\infty} a_{n}x^n - a_0 - a_1 x
$$

Levá strana:
$$
\sum_{n=2}^{\infty} a_n x^n = A(x) - a_0 - a_1 x
$$

$$
= A(x) - x
$$

Pravá strana:
$$
\sum_{n=2}^{\infty} a_{n-1} x^n$$

- posunutí - vytkneme $x$:

$$ 
= x \sum_{n=2}^{\infty} a_{n-1} x^{n-1}
$$
- přeindexujeme od $n=1$:
$$
= x \sum_{n=1}^{\infty} a_{n} x^{n} = x A(x)
$$


Druhá část pravé strany:
$$
\sum_{n=2}^{\infty} a_{n-2} x^n
$$
- posunutí - vytkneme $x^2$:
$$
= x^2 \sum_{n=2}^{\infty} a_{n-2} x^{n-2}
$$

$$
= x^2 A(x)
$$

Celá rovnice:
$$
A(x) - x = x A(x) + x^2 A(x)
$$

$$
A(x) (1 - x - x^2) = x
$$

$$
A(x) = \frac{x}{1 - x - x^2}
$$

#### Převedeme zpět na otevřený tvar pomocí parciálních zlomků.

$$
\frac{x}{1 - x - x^2}
= \frac{A}{1 - \alpha x} + \frac{B}{1 - \beta x}
$$

$$
(1 - x - x^2) = (1 - \alpha x)(1 - \beta x)
= 1 - (\alpha + \beta)x + \alpha \beta x^2
$$

$$
\alpha + \beta = 1
$$

$$
\alpha \beta = -1
$$

$\beta = 1 - \alpha$

$\alpha(1 - \alpha) = -1$

$\alpha - \alpha^2 = -1$

$\alpha^2 - \alpha - 1 = 0$

- $\alpha_{1,2} = \frac{1 \pm \sqrt{5}}{2}$

#### Spočítáme A a B:
$$
0 + x = A(1 - \beta x) + B(1 - \alpha x)
$$

$$
A + B = 0
$$

$$
- A \beta - B \alpha = 1
$$

$$
A = \frac{1}{\sqrt{5}}
$$
$$
B = -\frac{1}{\sqrt{5}}
$$

### Řešení:

$$
\sum_{n=0}^{\infty} a_n x^n
= \frac{1}{\sqrt{5}} \cdot \sum_{n=0}^{\infty} \alpha^n x^n - \frac{1}{\sqrt{5}} \cdot \sum_{n=0}^{\infty} \beta^n x^n
$$

$$
= \frac{1}{\sqrt{5}} \cdot \sum_{n=0}^{\infty} (\alpha^n - \beta^n) x^n
$$