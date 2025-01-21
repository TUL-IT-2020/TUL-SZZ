# Subfaktoriál

> [!question]
> Kolik existuje permutací na n-prvkové množině, kde žádný prvek není na svém místě.

Permutace:
1, 2, ..., n
$\pi(1), \pi(2), ..., \pi(n)$

Cyklus délky jedna -> prvek je na svém místě.

> [!tip] Subfaktoriál (řádu n)
>- $D(n), D_n$ - počet permutací na n-prvkové množině, kde žádný prvek není na svém místě.

## Selská úvaha
$D(n)$ odvodíme pomocí IE.

$\alpha(i)$ - i-tý prvek je na svém místě

$$
D(n) = N(\bar \alpha_1, \bar \alpha_2,\bar \alpha_2,...,\bar \alpha_n) =
N - 
\sum_{i=1}^n N(\alpha_1) +
\sum_{i<i_1<i_2\leq n}^n N(\alpha_{i_1},\alpha_{i_2}) + 

$$

$N = n!$ - počet všech permutací
$N(\alpha_1) = N(\alpha_2) = ... = N(\alpha_n) = (n-1)!$
$N(\alpha_{i_1},\alpha_{i_2}) = (n-2)!$
...
$N(\alpha_{i_1},...,\alpha_{i_n}) = (n-k)!$
...
$N(\alpha_1,...,\alpha_n) = 0!$

$$
D(n) = n! 
- (n-1)! * C_n^1 
+ (n-2)! * C_n^2 + ...
+ (-1)^k (n-k)!C_n^k + ... 
+ (-1)^n (0)!C_n^n
$$

Rozepíšeme členy n nad k a zkrátíme členy $(n-i)!$
$$
D(n) = n! \left[
1 - \frac{1}{1!} + \frac{1}{2!} + ... 
+ (-1)^k \frac{1}{k!}
+ ...
+ (-1)^n \frac{1}{n!}
\right]
$$
V hranatých závorkách máme částečný součet rozvoje $e^{-1}$.

$$
D(n) = round\left(\frac{n!}{e}\right)
$$
přibližně: $e^{-1}$

## Rekurentní vztah pro $D(n)$
$D(n) = (n-1)(D(n-1) + D(n-2))$
$D(n) = nD(n-1)+(-1)^n$

- $D(0) = 1$
- $D(1) = 0$
- $(D(2) = 1)$

Permutace jednoho prvku:
1
1

NHR

$P(n) = (n-1)(P(n-1)+P(n-2))$
$P(n) = nP(n-1)$

Žádný prvek není na svém místě. 
Rozdělíme $n-1$ tříd: $A_2,...,A_n$

- $A_i; \; i = 2,...,n$ - permutace, kde žádný prvek není na svém místě a na první pozici je $i$.

$D(n) = (n-1)|A_2|$

| permutace prvků   | D      |
| ----------------- | ------ |
| a_2, a_1,...      | D(n-2) |
| a_2, not a_1, ... | D(n-1) |
$D(n) = (n-1)(D(n-1 + D(n-2))$

$$
h_n = D(n) - nD(n-1) = (n-1)(D(n-1)+D(n-2)) -nD(n-1) 
$$
$$
h_n = -D(n-1) + (n-1)D(n-2)
$$

$$
h_n = (-1)^n
$$

## $D(n,k)$
> [!question]
Kolik je permutací na n-prvkové množině, kde právě k-prvků je na svém místě.

>[!tip]
>$D(n,k); D_{n,k}$ - označujeme počet permutací na prvkové množině, kde právě k prvků je na svém místě.

$$
D(n,k) = C_n^k D(n-k)
$$

$$
\sum_{k=0}^n D(n,k) = n! = \sum_{k=0}^n C_n^k D(n-k)
$$

> [!question]
Kolik je průměrný počet náhodně zapojených vstupů a výstupů?