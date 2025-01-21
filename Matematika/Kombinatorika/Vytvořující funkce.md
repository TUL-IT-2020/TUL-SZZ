# Vytvořující funkce
Obyčejnou vytvořující funkcí posloupnosti $\{a_n\}_{n=0}^\infty$ rozumíme algebraický výraz (formální mocninou řadu, respektive jakýkoliv výraz s ním ekvivalentní).

$$
f(x) = \sum_{n=0}^\infty a_n x^n
$$
Tedy:
$$
a_0 + a_1 x + a_2 x^2 + ... + a_n x^n + ...
$$

Příklad:
$$
a_n = (\frac{2}{3})^n
$$
Geometrická posloupnost:
$$
f(x) = \sum_{n=0}^\infty x^n = \frac{3}{3-2x}
$$

## f(x) může mít tvary:
### formální mocninná řada
$$
a_0 + a_1 x + a_2 x^2 + ... + a_n x^n + ...
$$
Vidíme tvar jednotlivých členů posloupnost.

### uzavřený tvar vytvořující funkce
Konečný výraz.

## Postup řešení
$$
\{a_n\} ... f(x) = \sum a_n x^n
$$
1. Máme otevřený tvar.
2. Hledáme uzavřený tvar $f(x)$.
Manipulace s funkcemi.
2. Nový uzavřená tvar $g(x)$.
3. Otevřený tvar $g(x) -> {b_n}$.

Přechod mezi těmi to stavy jsou úlohy které můžeme řešit.

Existuje vzájemně jednoznačný vztah mezi posloupností a její vytvořující funkcí. 

[[Derivace|Zderivujeme]]:
- $a_0 = f(0)$
- $a_1 = dx f(0)$
- $a_2 = \frac{dx^2}{2} f(0)$

$$
a_n = \frac{dx^n}{n!} f(0)$
$$
## Převod mezi tvary
Otevřený <-> uzavřený tvar

Geometrická posloupnost:
$$
{q^n}_{n=0}^\infty = \frac{1}{1-qx}
$$
Kombinační číslo (binomický koeficient):
$$
{C_n^k}_{k=0}^\infty = (1+x)^n
$$
- $n \in Z$

TODO: napiš n nad k
$C_n^k = \left(n k\right)$

$$
\left\{\frac{q^n}{n!}\right\} = e^{qx}
$$

Velmi často bude uzavřený tvar vytvořující funkce:

$$
f(x) = \frac{P(x)}{Q(x)}
$$
Kde:
- $P(x), Q(x)$ jsou polynomy.

Rozklad na parciální zlomky.

## Manipulace s vytvořujícími funkcemi
Posloupnosti:
- $\{a_n\}_{n=0}^\infty = f(x)$
- $\{b_n\}_{n=0}^\infty = g(x)$

|                                    | vytvořující funkce                                                   | posloupnost                                                                          |
| ---------------------------------- | -------------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| lineární kombinace                 | $\alpha f(x) + \beta g(x)$, $\alpha, \beta \in R$                    | $\{\alpha a_n + \beta b_n\}$                                                         |
| shift left                         | $$\frac{f(x) - (a_0+a_1x+...+a_{k-1}x^{k-1})}{x^{k-1}}$$ $k \in N^+$ | $a_k, a_{k+1},...$                                                                   |
| shift right                        | $x^k f(x), k \in N$                                                  | $kx0, a_0, a_1,...$                                                                  |
| proložení nulami                   | $f(x^k), k \in N^+$                                                  | $a_0,(k-1)x0,a_1,(k-1)x0,...$                                                        |
| derivace                           | $f´(x)$                                                              | $\{(n+1) a_{n+1} \}_{n=0}^\infty$                                                    |
| integrál                           | $\int_0^x f(t) dt$                                                   | $0, a_0, a_1/2, a_2/3,..., a_n / n+1,...$                                            |
| konvoluce: násobení každý s každým | $f(x)g(x)$                                                           | $a_0 * b_0, a_0*b_1 + a_1*b_0, ...$<br>$$\{\sum_{i=0}^n a_i b_{n-i}\}_{n=0}^\infty$$ |
|                                    |                                                                      |                                                                                      |

Příklad:
Určete uzavřený tvar posloupnosti: $a_n = n$

- $a_n = 1$
$$
f(x) = \frac{1}{1-x}
$$
Derivace:
$1,2,3, ...$
$$
f_1(x) = \frac{1}{(1-x)^2}
$$

$1+2x+3x^2+....+nx^{n-1}$
$$
\{x\}_{n=0}^\infty = \frac{x}{(1-x)^2}
$$
## Exponenciální vytvořující funkce
![[Exponenciální vytvořující funkce]]

## Aplikace vytvořujících funkcí
Řešení rekurentních vztahů metodou vytvořujících funkcí. 

NHLR:
$$
C_ka_{n+k} + ... + c_0 a = p_n
$$

$$
\{a_n\}_{n=0}^\infty ... f(x) = \sum a_n x^n
$$


Myšlenka:
Nalezneme uzavřený tvar vytvořující funkce.
$$
f(x)
$$
A následně jeho rozvinutý tvar.

Učitel by měl vždy říci žákům proč se danou věc učí. 
Vyučuj s příběhem. 
Příběh ve kterém je definovaný problém, který lze vyřešit aplikací daných znalostí.

Obě strany vynásobíme: $x^{n+k}$
$$
C_ka_{n+k} * x^{n+k} + ... + c_0 a * x^{n+k} = p_n * x^{n+k}
$$

Sesumujeme: $\sum_{n=0}^\infty$
$$
C_k \sum_{n=0}^\infty a_{n+k} * x^{n+k} 
+ ... + 
c_0 x^k \sum_{n=0}^\infty a_n *x^{n} 
= x^k \sum_{n=0}^\infty p_n x^{n}
$$
- nekonečné součty nahradíme symbolem pro vytvořující funkci.

$$
x^k c_0 f(x) = x^k p (x)
$$
Roznásobíme, převedeme členy bez $f(x)$ na jednu stranu.

Získáme uzavřený tvar.
$$
f(x) = ...
$$