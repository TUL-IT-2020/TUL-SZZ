# Exponenciální vytvořující funkce příklady

## Příklad EGF

$a_n = n a_{n-1}$
- $a_0 = 1$

> [!note]
> To je přece faktoriál: $a_n = n!$

### Postup:
$$
\hat A(x) = \sum_{n=0}^{\infty} a_n \frac{x^n}{n!}
$$

Vynásobit $\frac{x^n}{n!}$:
$$  
\sum_{n=0}^{\infty} a_{n+1} \frac{x^n}{n!} 
= \sum_{n=0}^{\infty} (n+1) a_n \frac{x^n}{n!}
$$

> [!tip] "derivace"
> A ta $n$ se pak požerou.

![[Derivace exponenciální vytvořující funkce]]

$$
a_{n+1} = (n+1) a_n
$$

$$
\sum_{n=0}^{\infty} a_{n+1} \frac{x^n}{n!}
= \sum_{n=0}^{\infty} (n+1) a_n \frac{x^n}{n!}
$$

$$
= \hat A'(x) \cdot \sum_{n=0}^{\infty} a_n \frac{x^n}{n!} + \sum_{n=0}^{\infty} na_n \frac{x^n}{n!}
$$

$$
= \hat A'(x) = \hat A(x) + x \hat A'(x)
$$

Hele derivace součinu!
$$
(fg)' = f'g + fg'
$$

Notes

$$
x \sum_{n=1}^{\infty} a_n \frac{x^{n-1}}{(n-1)!} = 
$$

$$
= x \sum_{k=0}^{\infty} a_{k+1} \frac{x^{k}}{k!}
$$

> [!tip]
$$
(x \hat A(x))' = \hat A(x) + x \hat A'(x)
$$

$$
\hat A'(x) = (x \hat A(x))' 
$$

Tak to z integrujeme!

$$
A(x) = xA(x) + C
$$

$$
A(0) = a_0
$$

$$
1 = 0 + C
$$

$$
C = 1
$$

$$
A(x) (1-x)= 1
$$

Uzavřený tvar:
$$
A(x) = \frac{1}{1-x}
$$

$$
A(x) = \sum_{n=0}^{\infty} x^n
$$


$$
\frac{1}{1-x} = \sum_{n=0}^{\infty} x^n
$$

$$
\sum_{n=0}^{\infty}  n! \frac{x^n}{n!} 
$$

Jediné možné řešení:
$$
\frac{a_n}{n!} = 1
$$

$$
a_n = n!
$$


## Příklad EGF
$$
a_{n+1} = (n+1) a_n + 2^n
$$

- $a_0 = 0$

> [!note]
> Obecná exponenciální vytvořující funkce:
$$
\hat A(x) = \sum_{n=0}^{\infty} a_n \frac{x^n}{n!}
$$

### Postup:

Vynásobit $\frac{x^{n+1}}{(n+1)!}$:
$$
\sum_{n=0}^{\infty} a_{n+1} \frac{x^{n+1}}{(n+1)!} 
= \sum_{n=0}^{\infty} (n+1) a_n \frac{x^{n+1}}{(n+1)!} + \sum_{n=0}^{\infty} 2^n \frac{x^{n+1}}{(n+1)!}
$$

LS:
$$
\sum_{n=0}^{\infty} a_{n+1} \frac{x^{n+1}}{(n+1)!} 
= \hat A'(x) - a_0
= \hat A'(x) - 0
$$

PS:
$$
\sum_{n=0}^{\infty} (n+1) a_n \frac{x^{n+1}}{(n+1)!} 
= x \sum_{n=0}^{\infty} a_n \frac{x^n}{n!}
= x \hat A(x)
$$

Druhý člen PS:
$$
\sum_{n=0}^{\infty} 2^n \frac{x^{n+1}}{(n+1)!}
\Rightarrow e^x
$$

- $\hat A(x) = f(x)$

> [!tip]
$$
e^x = \sum_{n=0}^{\infty} \frac{x^n}{n!}
$$

$$
e^{2x} = \sum_{n=0}^{\infty} 2^n \frac{x^n}{n!}
$$

$$
1/2 \sum_{n=0}^{\infty} 2^{n+1} \frac{x^{n+1}}{(n+1)!}
$$

$$
= 1/2 (e^{2x} - 1)
$$

Celá rovnice:
$$
\hat A'(x) = x \hat A(x) + 1/2 (e^{2x} - 1)
$$

Řešíme rovnici:
$$
\hat A'(x) - x \hat A(x) = 1/2 (e^{2x} - 1)
$$

$$
A(x)(1-x) = 1/2 (e^{2x} - 1)
$$

$$
A(x) = \frac{e^{2x}-1}{2} \cdot \frac{1}{1-x}
$$

$$
\sum_{n=0}^{\infty} \sum_{k=0}^{n} \binom{n}{k} c_k b_{n-k} x^n
$$

### Řešení:
$$
a_n = 1/2 \sum_{k=1}^{n} \binom{n}{k} 2^k \cdot (n-k)!
$$