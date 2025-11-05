# Exponenciální vytvořující funkce příklady

## Příklad

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

"derivace"