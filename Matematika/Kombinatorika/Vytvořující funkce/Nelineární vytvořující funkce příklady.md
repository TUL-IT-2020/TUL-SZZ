# Nelineární vytvořující funkce příklady

## Příklad
$$
a_{n+1} = a_n + \sum_{k=0}^{n-1} a_k a_{n-1-k}
$$

- $a_0 = 1$
- $a_1 = 1$

> [!note] Obecná vytvořující funkce:
$$
A(x) = \sum_{n=0}^{\infty} a_n x^n
$$

### Postup:
Čím to přenásobit?
- $x^n$
- $x^{n+1}$
  
$$
\sum_{n=1}^{\infty} a_{n+1} x^{n+1} = \sum_{n=1}^{\infty} a_n x^{n+1} + \sum_{n=1}^{\infty} \left( \sum_{k=0}^{n-1} a_k a_{n-1-k} \right) x^{n+1}
$$

Přeindexujeme:

LS:
$$
\sum_{n=1}^{\infty} a_{n+1} x^{n+1} = \sum_{n=2}^{\infty} a_n x^n
$$

$$
\sum_{n=2}^{\infty} a_n x^n = A(x) - a_0 - a_1 x = A(x) - 1 - x
$$

PS:
- vytáhneme $x$ před sumu
$$
x \sum_{n=1}^{\infty} a_n x^n +
$$

- vytáhneme $x^2$ před sumu, aby seděli rozsahy sum
$$
+ x^2 \sum_{n=1}^{\infty} \left( \sum_{k=0}^{n-1} a_k a_{n-1-k} \right) x^{n-1}
$$

- $m = n-1$
- Nahradíme, posuneme indexy
$$
x^2 \sum_{m=0}^{\infty} \left( \sum_{k=0}^{m} a_k a_{m-k} \right) x^{m}
$$

$$
= x^2 A(x)^2
$$

Celá rovnice:
$$
A(x) - 1 - x = x (A(x) - 1) + x^2 A(x)^2
$$

$$
A(x) - x A(x) + x - x^2 A(x)^2 - 1 - x = 0
$$

$$
x^2 A(x)^2  + A(x)(x  - 1) +1 = 0
$$

- $A(x) = ?$ 
- řešíme kvadratickou rovnici:

$$
A(x) = \frac{1 - x \pm \sqrt{(x-1)^2 - 4x^2}}{2x^2}
$$

$a_0 = 1$ ... Hledáme limitu při $x \to 0$

$$
\lim_{x \to 0} A(x) = 1
$$

$$
\lim_{x \to 0+} \frac{1 - x - \sqrt{(x-1)^2 - 4x^2}}{2x^2} = \lim_{x \to 0+} \frac{0}{0}
$$

$$
\lim_{x \to 0+} \frac{1 - x + \sqrt{(x-1)^2 - 4x^2}}{2x^2} = \lim_{x \to 0+} \frac{2}{0} = \infty
$$

Zkusíme pokračovat s tou první.

Determinant uvnitř odmocniny:
$$
(x-1)^2 - 4x^2 = x^2 - 2x + 1 - 4x^2 = 1 - 2x - 3x^2
$$

Odbočka na binomickou větu a Taylorův rozvoj:

> [!tip]
$$
(1 + u)^{\alpha} = \sum_{k=0}^{\infty} \binom{\alpha}{k} u^k
$$

$$
\sqrt{1 - 2x - 3x^2} = (1 + (-2x - 3x^2))^{\frac{1}{2}} =
$$
$$
= \sum_{k=0}^{\infty} \binom{\frac{1}{2}}{k} (-2x - 3x^2)^k
$$

A mnoho dalšího voodoo...

### Řešení:
$$
a_n =
$$

> [!note]
> U zkoušky to nebude.
