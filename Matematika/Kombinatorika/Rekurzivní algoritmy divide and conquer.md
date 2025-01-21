# Rekurzivní algoritmy divide and conquer
> [!tip] Rozděl a panuj
> - f(n) - časová složitost alg. pro rozsah n
>$$
f(n) = a f\left( \lceil n/b \rceil \right) + h(n)
$$

> [!example] Kde:
>- $a$ - počet pod úloh $a \in N^+$
>- $\lceil n/b \rceil$ - rozsah pod-úloh $b \in N - \{0,1\}$
>- $h(n)$ - časová složitost rozdělení na pod úlohy a časová složitost sestavení řešení původní úlohy z řešení pod úloh.
>- $f(1) = c$ - počáteční podmínka $c \in R^+$ 

## Konstantní čas pro rozdělení na pod-úlohu a sestavení řešení.
> [!note] 
>$$
h(n) = c
$$

$n \in S_b = \{b^k | k \in N \}$
$$
f(n = b^k) = a f (b^{k-1}) + c
$$
$$
f(b^k-1) = a f (b^{k-2})+c
$$


$$
f(n) = c (a^k + a^{k-1} + ... + a +1)
$$

$a = 1$
$f(n) = c(k+1)$

$a > 1$
$f(n) = c \frac{a^{k+1}-1}{a-1}$

$n > b^k$
$log_b (n) = k$

$a^k = a ^{log_b(n)}= (b^{log_b{a}})^ {log_b{n}} = n ^ {log_b a }$


Nechť $f(n)$ je rostoucí na N taková že na množině $S_b \{b^k | k \in N\}$ platí:
$$
f(n) \leq a f(n/b) + c
$$
- $f(1) \leq c$

Potom:
- Pro $a = 1$
$$
f(n) \in O(log_b n)
$$
- Pro $a \geq 2$
$$
f(n) \in O(n^{log_b a})
$$


## Ne konstantní čas pro rozdělení na pod-úlohu a sestavení řešení.
> [!note]
> $$
h(n) = r n^d
$$
- $r \in R^+$
- $d \in N^+$

Platí:
Nechť $f(n)$ je rostoucí na N taková že na množině $S_b \{b^k | k \in N\}$ platí:
$$
f(n) \leq a f(n/b) + rn^d
$$
- $f(1) \leq c$

Potom platí:
- pro $a < b^d$
$$
f(n) \in O(n^d)
$$
- pro $a = b^d$
$$
f(n) \in O(n^d log_bn)
$$
- pro $a > b^d$
$$
f(n) \in O(n^{log_ba})
$$