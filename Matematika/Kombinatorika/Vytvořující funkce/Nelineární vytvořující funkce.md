# Nelineární vytvořující funkce

Nelineární posloupnosti.

"Catalanovo číslo" - počet správně zanořených závorek.

> [!note]
> Konvoluce dvou posloupností:
$$
c_{n+1} = \sum_{k=0}^{n} c_k c_{n-k}
$$

- $c_n =$ ?

$$
\sum_{n=0}^{\infty} c_{n+1} x^n = 
\sum_{n=0}^{\infty} \left( \sum_{k=0}^{n} c_k c_{n-k} \right) x^n
$$

> [!tip]
> Součin dvou vytvořujících funkcí odpovídá konvoluci jejich posloupností.

$$
A(x)B(x) = \sum_{n=0}^{\infty} \left( \sum_{k=0}^{n} a_k b_{n-k} \right) x^n
$$

$$
\sum_{n=0}^{\infty} c_{n+1} x^n = C(x)^2
$$

Indexy, obě strany vynásobíme $x$:
$$
\sum_{n=0}^{\infty} c_{n+1} x^{n+1} = x C^2(x)
$$

$$
C(x) - c_0 = x C^2(x)
$$

$$
C(x) - 1 = x C^2(x)
$$

$$
x C^2(x) - C(x) + 1 = 0
$$

Řešíme kvadratickou rovnici:
$$
C(x) = \frac{1 \pm \sqrt{1 - 4x}}{2x}
$$

- $c_0 = 1$

$$
lim_{x \to 0} C(x) = ?
$$


$$
C(0) = \lim_{x \to 0} = c_0
$$

Co takhle Taylorův rozvoj?

![[Binomická věta]]

$$
(1 + x)^{1/2} = 
1 + 1/2 x - 1/8 x^2 + 1/16 x^3 - 5/128 x^4 + ...
$$

$$
(1 - 4x)^{1/2} = 1 - 2x - 2x^2 - \frac{8}{3} x^3 - 5x^4 + ...
$$

$$
\frac{1-(1-2x)}{2x} \rightarrow 1
$$

Vyloučili jsme kladnou větev.

$$C(x) = \frac{1 - (1 - 4x)^{1/2}}{2x}$$

> [!note]
$$
(1 + x)^{\alpha} = \sum_{k=0}^{\infty} \binom{\alpha}{k} x^k
$$

- $\alpha = 1/2$
- $x \rightarrow -4x$



$$
C(x) = \frac{1 - (1+ \sum_{k=1}^{\infty} \binom{1/2}{k} (-4x)^k)}{2x}
$$

$$
= \frac{-1}{2} \sum_{k=1}^{\infty} \binom{1/2}{k} (-4)^{k} x^{k-1}
$$

$$
C(x) = \frac{-1}{2} \sum_{n=0}^{\infty} \binom{1/2}{n+1} (-4)^{n+1} x^{n}
$$

$$
C(x) = 2 \sum_{n=0}^{\infty} \binom{1/2}{n+1} (-1)^{n} 4^{n} x^{n}
$$

Řešení pro členy posloupnosti:
$$
c_n = 2 (-1)^{n} 4^{n} \binom{1/2}{n+1}
$$

Lze dokázat indukcí, že:
$$
c_n = \frac{1}{n+1} \binom{2n}{n}
$$

## Příklady

![[Nelineární vytvořující funkce příklady]]