# Rozklady

![[Třídy rozkladu množiny]]

n - objektů (prvků) rozdělujeme (rozkládáme) do tříd (skupin).

Objekty mohou být:
- nerozlišitelné,
- rozlišitelné.

Třídy mohou být:
- nerozlišitelné,
- rozlišitelné.

## Úlohy
### N nerozlišitelných objektů do rozlišitelných tříd
![[N nerozlišitelných objektů do rozlišitelných tříd]]

### N nerozlišitelných objektů rozkládáme do k tříd, v i-té třídě je alespoň $a_i$ objektů.
![[N nerozlišitelných objektů rozkládáme do k tříd, v i-té třídě je alespoň $a_i$ objektů.]]

### N nerozlišitelných objektů rozkládáme do k rozlišitelných tříd, v i-té tříde je alespoň $a_i$ a nejvýše $b_i$ objektů
![[N nerozlišitelných objektů rozkládáme do k rozlišitelných tříd, v i-té tříde je alespoň $a_i$ a nejvýše $b_i$ objektů]]
## Řešení těchto úloh pomocí: vytvořujících funkcí
$$
x_1 + x_2 + ... + x_k = n
$$
$(1+x+x^2+...)$

Konvoluce:
$$
f(x) = (1+x+x^2+...)^k
$$

Uzavřený tvar:
$$
\frac{1}{1-x}
$$

$$
f(x) = \frac{1}{(1-x)^k} = (1-x)^{-k}
$$

Když:
$a_i \leq x_i$

Změna:
$$
f(x) = \prod_{i=1}^k (x^{a_i}+x^{a_i+1}+...)
$$
$$
f(x) = \frac{x^{\sum_{i=1}^k a_i}}{(1-x)^k} = x^{\sum_{i=1}^k a_i} a_i (1-x)^{-k}
$$

Když:
$a_i \leq x_i \leq b_i$

$$
f(x) = \prod_{i=1}^k (x^{a_i}+x^{a_i+1}+...+x^{b_i})
$$
$$
f(x) = \prod_{i=1}^k x^{a_i}(1+x+...+x^{b_i-a_i})
$$

$$
\frac
{1-x^{b_i-a_i+1}}
{1-x}
$$

### N nerozlišitelných objektů rozkládáme do nerozlišitelných tříd
![[N nerozlišitelných objektů rozkládáme do nerozlišitelných tříd]]

### N rozlišitelných objektů rozkládáme do k neprázdných tříd

![[N rozlišitelných objektů rozkládáme do k neprázdných tříd]]

### Rozkládáme n prvkovou množinu do k neprázdných cyklů
![[Rozkládáme n prvkovou množinu do k neprázdných cyklů]]

## Stirlingova čísla 1. a 2. druhu
![[Stirlingova čísla 1. a 2. druhu]]