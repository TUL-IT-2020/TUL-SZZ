# Exponenciální vytvořující funkce
Exponenciální vytvořující funkcí $\{a_n\}_{n=0}^\infty$ rozumíme algebraický výraz (formální mocninnou řadu)

$$
\hat A(x) = f(x) = \sum_{n=0}^\infty a_n \frac{x^n}{n!}
$$

> [!note]
"$a_n = n a_{n-1}$"

Respektive jakýkoliv s ním ekvivalentní výraz.

Existuje vzájemně jednoznačný vztah mezi posloupností a její exponenciální vytvořující funkcí.

$$
a_n = f^{(n)} (0)
$$

| posloupnost | Obyčejná         | Exponenciální |
| ----------- | ---------------- | ------------- |
| 1,1,1,1,... | $\frac{1}{1-x}$  | $e^x$         |
| $\{q^n\}$   | $\frac{1}{1-qx}$ | $e^{qx}$      |

$C_n^k = (1+x)^n$ ... kombinace
$A^k_n$... variace k-té třídy z n prvků

$$
A_n^k = \frac{n!}{(n-k)!}
$$

## Základní operace

Součet:
$$
\hat A(x) + \hat B(x) = \sum_{n=0}^\infty (a_n + b_n) \frac{x^n}{n!}
$$

Součin:
$$
\hat A(x) \cdot \hat B(x) = \sum_{n=0}^\infty \left( \sum_{k=0}^n \binom{n}{k} a_(n-k) b_{k} \right) \frac{x^n}{n!}
$$

Posunuti:
$$
x \hat A(x) 
= x \sum_{n=0}^\infty a_n \frac{x^{n}}{n!} 
= \sum_{n=0}^\infty a_{n} \frac{x^{n+1}}{n!}
$$

> [!note] Picek:
> "Já v tom nevidím co jsem chtěl vidět!"

$$
= \sum_{m=1}^\infty a_{m-1} \frac{x^{m}}{(m-1)!}
$$

$$
= \sum_{m=1}^\infty m a_{m-1} \frac{x^{m}}{m!}
$$

- $(0, a_0, 2a_1, 3a_2, ...)$
  
## Tabulka základních exponenciálních vytvořujících funkcí

| posloupnost         | exponenciální v.f.: $\hat A(x)$ |
| ------------------- | -------------------- |
| $1,1,1,1$           | $e^x$                |
| $n!$               | $\frac{1}{1-x}$      |
| $n$               | $x e^x$              |
| $n^2$             | $(x^2 + x) e^x$ |

## Příklady

- [[Exponenciální vytvořující funkce příklady]]