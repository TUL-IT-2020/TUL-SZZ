#příklad 
# Bézoutova rovnost

Online kalkulačka [Bezutova rovnost](https://wims.univ-cotedazur.fr/wims/wims.cgi?session=UNF26DBBB6.2&lang=en&cmd=reply&module=tool%2Farithmetic%2Fbezout.en&x1=70705&x2=12530&bezout=yes&euc1=1&euc2=2)

## Příklad
Pro a = 10959, b = 37999 vyjádřete $NSD(a, b)$ ve tvaru $ax_0 + by_0$.
### Postup
|  | = |  | x | $q_i$ | + | $r_i$ |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| 37999 |  | 10959 |  | 3 |  | 5122 |
| 10959 |  | 5122 |  | 2 |  | 715 |
| 5122 |  | 715 |  | 7 |  | 117 |
| 715 |  | 117 |  | 6 |  | 13 |
| 117 |  | 13 |  | 9 |  | 0 |
$NSD(a,b) = 13$

| i | -1 | 0 | 1 | 2 | 3 | 4 |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| $q_i$ | / | 3 | 2 | 7 | 6 | 9 |
| $P_i$ | 1 | 3 | 7 | 52 | 319 | 2923 |
| $Q_i$ | 0 | 1 | 2 | 15 | 92 | 843 |
Zajímají nás čísla v předposledním sloupečku. Pozici znaménka určujeme tak aby nám vyšlo kladné NSD(a,b).
### Řešení
$NSD(a,b) = 13 = 10959*(319) + 37999*(-92)$

## Příklad
Pro a = 583, b = 231 vyjádřete $NSD(a, b)$ ve tvaru $ax_0 + by_0$.

### Postup
Aplikací [[Euklidův algoritmus|Eukleidova algoritmu]] dostáváme:
$583 = 231* 2+ 121$ (r1)
$231 = 121 * 1 + 110$ (r2)
$121 = 110*1+11$ (r3)
$110 = 11 *10 +0$

tedy $NSD(583,231) = 11 (r_3)$. 

Postupným „zpětným” vyjádřením zbytku $r_3$ dostáváme:
$r_3 = 11 = 121 - (231-121*1)*1 = 121*2-231 =$ 
$=(583 - 231 * 2) * 2 - 231 = 583 * 2 + 231 * (-5)$
tedy:
$NSD(583, 231) = 11 = 583 *2 + 231 *(-5)$
### Řešení
$NSD(583, 231) = 11 = 583 *2 + 231 *(-5)$

## Příklad
Pro a = 13440, b = 19740 vyjádřete $NSD(a, b)$ ve tvaru $ax_0 + by_0$.

### Postup
a = 13440 = 20 * 672
b = 19740 = 20 * 987

| dělenec | dělitel | $q_i$ | zbytek |
| ---- | ---- | ---- | ---- |
| 987 | 672 | 1 | 315 |
| 672 | 315 | 2 | 42 |
| 315 | 42 | 7 | 21 |
| 42 | 21 | 2 | 0 |
NSD(a,b) = 20 * 21 = 420

$$
1 = \frac{ax_0+by_0}{420} = \frac{ax_0}{420} + \frac{by_0}{420}
$$
$13440:420 = 32$
$19740:420 = 47$

### Řešení
$NSD(a,b) = 420 = ax_0+by_0 = a*(-22) + b*(15)$

## Příklad
Pro a = 70705, b = 12530 vyjádřete $NSD(a, b)$ ve tvaru $ax_0 + by_0$, tedy Bezutovy rovnosti.

### Postup
|  | = |  | x | $q_i$ | + | $r_i$ |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| 70705 |  | 12530 |  | 5 |  | 8055 |
| 12530 |  | 8055 |  | 1 |  | 4475 |
| 8055 |  | 4475 |  | 1 |  | 3580 |
| 4475 |  | 3580 |  | 1 |  | 895 |
| 3580 |  | 895 |  | 4 |  | 0 |
Tabulka řetězových zlomků:

| i | -1 | 0 | 1 | 2 | 3 | 4 |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| $q_i$ | / | 5 | 1 | 1 | 1 | 4 |
| $P_i$ | 1 | 5 | 6 | 11 | 17 | 79 |
| $Q_i$ | 0 | 1 | 1 | 2 | 3 | 14 |
### Řešení
$NSD(a,b) = 895 = a*(-3) + b*(17)$