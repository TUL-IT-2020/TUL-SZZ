# Nehomogenní lineární rekurentní vztahy

> [!tip] Definice:
Nehomogenním lineárním rekurentním vztahem řádu $k$ s konstantními koeficienty rozumíme výraz:
$$
C_ka_{n+k} + C_{k-1}a_{n+k-1} + ... + c_0 a = p_n
$$
> [!example] Kde:
- $C_i \in R$
- $C_k*C_0 \neq 0$
- $\exists n_0 \in N, p \neq 0$
- $\{p_n\}_{n=0}^{infty}$ není identicky 0, posloupnost

> [!danger] NHLR(\*\*)

## Řešení
Platí:
- Má nekonečně mnoho řešení pro libovolnou pravou stranu $p_n$.
- S $k$ počátečních podmínek má NHLR právě jedno řešení.

> [!tip] Obecné řešení NHLR je tvaru:
$$
a_n = a_n^{(h)} + a_n^{(p)}
$$

> [!example] Kde:
- $\{a_n^{h}\}$ je obecné řešení příslušného [[Homogenní lineární rekurentní vztahy|HLR]]
- $\{a_n^{p}\}$ je partikulární řešení NHLR (částečné řešení, jedno konkrétní, které vyhovuje NHLR)

Postup:
$$
a_{a+k} = p_n - \frac{1}{C_k}\left(C_{k-1}a_{n+k-1}+...+C_0a_n \right)
$$


$\{a_n^{p}\};\{a_2\}$ jsou řešení NHLR

$$
C_k(a_{n+k}-a_{n+k}^p)+...+C_0(a_n-a_n^p) = 0
$$
$$a_n - a_n^p = a_n^p$$
> [!tip] Závěr:
Vyřešit NHLR znamená umět nalézt příslušné partikulární řešení $a_n^p$.

Myšlenka:
Partikulární řešení hledáme ve tvaru pravé strany. 

Postup:

1) Zkušební řešení (ve tvaru pravé strany) $\{t_n\}^\infty_{n=0}$ ve tvaru pravé strany $p_n$ NHLR. Využijeme níže uvedenou tabulku zkušebních řešení. 

| $p_n$            | $t_n$                                                     |
| ---------------- | --------------------------------------------------------- |
| K (konstanta)    | A (konstanta)                                             |
| $n^t, t\in N$    | $A_0 + A_1n+...+A_tn^t$ - polynom stupně t, A - konstanta |
| $r^n,r\in R$     | $Ar^n$                                                    |
| $r^n*n>t,t\in R$ | $r^n(A_0 + A_1n+...+A_tn^t)$                              |
| $cos(\alpha n)$  | $A cos(\alpha n) + B \sin/(\alpha n)$                     |
| $sin(\beta n)$   | $A cos(\beta n) + B \sin/(\beta n)$                       |

Jestliže je pravá strana $p_n$ je lineární kombinací výrazů $p_n$ uvedených v tabulce, potom zkušební řešení je lineární kombinací příslušných $t_n$ z tabulky. 

Jestliže žádný ze sčítanců, zkušebního řešení není řešení příslušného HLR, potom:
$$
a_n^p = t_n
$$

Jestliže některý ze sčítanců zkušebního řešení $t_n$ je řešením příslušného HLR, potom:
$$
a_n^p = n^st_n
$$

kde s je nejmenší přirozené číslo takové, že žádný ze sčítanců $n^s*t_n$ již není řešením příslušného HLR.

> [!note] Funky note:
$$
\lim_{n->\infty} \frac{F_{n+1}}{F_n} = \frac{1+\sqrt{5}}{2}
$$
... zlatý řez

## Příklady
- [[NHLR příklady]]