# Zákon velkých čísel
## Průměr
Uvažujme $𝑛$ nezávislých měření (=náhodných veličin) $X_1, X_2, … , X_n$. [[Náhodná veličina|Náhodnou veličinu]]: 
$$
\frac{1}{n} \sum^{n}_{i=1} X_i 
$$
nazveme **průměr**.
Pro $n \rightarrow \infty$ označme posloupnost $(X_n)^{\infty}_{n=1}$.

## ZVČ
Nechť $X_1,X_2,...,X_n$ je posloupnost [[Statistická závislost a nezávislost#I.I.D. (independent identically distributed)|i.i.d.]] náhodných veličin, pro které existuje $\mu = E[X_i]$ a $\sigma^2 = E[(X_i - \mu)^2]$ pro všechna i. Pak platí:
$$
\lim_{n \rightarrow \infty} \frac{1}{n} \sum^{n}_{i=1} X_i = \mu
$$
- $\lim_{n \rightarrow \infty}$ ... průměr
- $\mu$ ... střední hodnota

## Příklady:
1. [[Gaussovo (normální) rozdělení|Gaussovo rozdělení]]
2. [[Cauchyho rozdělení|Cauchyho standardní rozdělení]]
$$
f_X(x) = \frac{1}{\pi(1+x^2)}
$$
### Výsledky:
2. Nemá střední hodnotu ani rozptyl!