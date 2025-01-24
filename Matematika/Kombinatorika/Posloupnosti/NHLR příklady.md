# NHLR příklady

## Příklad
Určete posloupnost $\{a_n\}^\infty_{n=0}$, pro kterou platí: 
součet druhé diference v bodě n a první diference v bodě n+1 je roven $2n+3$.
- $a_0 = 6$
- $a_1 = 3$

### Postup
Vzorečky:
$$
\Delta a_n = a_{n+1} - a_n
$$
$$
\Delta^{(2)} a_n = a_{n+2} -2a_{n+1} + a_n
$$
Dosazeni:
$$
2n+3 = \Delta^{(2)} a_n + \Delta a_{n+1}
$$

$$
2n+3 = a_{n+2} -2a_{n+1} + a_n + a_{n+2} - a_{n+1}
$$
Úprava:
$$
2a_{n+2} - 3a_{n+1} + a_n = 2n+3
$$

Charakteristický polynom:
$$
2x^2 - 3x + 1 = 0
$$

Homogenní řešení (pravá strana je nulová):
$$
2x^2 - 3x + 1 = (x - 1)(2x - 1) = 0
$$
Kořeny:
- $x_1 = 1$
- $x_2 = \frac{1}{2}$

$$
a_n = C_1(1)^n + C_2(\frac{1}{2})^n
$$


Zkušební řešení:
- $(2n+3)$
$$
t_n = A_n + B 
$$

- $A_n$
- $B$

Jsou řešením homogenní rovnice?

- $B$ - konstanta -> je řešením, když $L = 0$

Tak to vynásobíme $n$:
$$
a_n^(p) = A_n^2 + Bn
$$

Určíme konstanty $A,B$:
$$
2a_{n+2} - 3a_{n+1} + a_n = 2n+3
$$

$$
2(A(n+2)^2 + B(n+2)) - 3(A(n+1)^2 + B(n+1)) + An^2 + Bn = 2n+3
$$
...

$$
a^p = n^2 -2
$$

- $A = 1$
- $B = -2$

Obecné řešení:
$$
a_n = K+L(1/2)^n + n^2 -2n
$$

Dosazením počátečních podmínek:
- $a_0 = 6 = K + L$
- $a_1 = 3 = -1 + K + \frac{1}{2}L$

$$
a_n = 2 - 2n + n^2 + 4(\frac{1}{2})^n
$$

### Řešení
$$
a_n = 2 - 2n + n^2 + 4(\frac{1}{2})^n
$$

## Příklad
$$
a_{n+2} - 2a_{n+1} + 4a_n = 3n+6
$$

- $a_0 = 3$
- $a_1 = 4+\sqrt{3}$

### Postup
- [[Kvadratická rovnice]]
- [[Komplexní čísla]]

Homogenní rovnice:
$$
x^2-2x+4=0
$$
Kořeny:
- $x_1 = 1 + i\sqrt{3}$
- $x_2 = 1 - i\sqrt{3}$

$$
a_n^h = C_1(1+i\sqrt{3})^n + C_2(1-i\sqrt{3})^n
$$

$$
(1\pm i\sqrt{3})^n = 2^n(\cos(\varphi n) \pm i\sin(\varphi n))
$$

Amplituda:
$$
\sqrt{1^2 + (\sqrt{3})^2} = 2
$$

Fáze:
$$
\varphi = \arctan(\frac{\sqrt{3}}{1}) = \frac{\pi}{3}
$$
Dosazeno:
$$
(1\pm i\sqrt{3})^n = 2^n(\cos(\frac{\pi}{3}n) \pm i\sin(\frac{\pi}{3}n))
$$

$$
(cos \varphi \pm i \sin \varphi)^n = \cos(n\varphi) \pm i \sin(n\varphi)
$$

Homogenní řešení:
$$
a_n^h = L_1 2^n \cos(\frac{\pi n}{3}) + L_2 2^n\sin(\frac{\pi n}{3})
$$

Zkušební řešení:
$$
t_n = An + B
$$
- $An$ - lineární funkce
- $B$ - konstanta

Je některý z sčítanců řěšením homogenní rovnice?
- NE

$$
a_n^p = [A(n+2) + B] - 2[A(n+1) + B] + 4[An + B] = 3n+6
$$

$$
a_n^p = An + 2A + B - 2An -2A - 2B + 4An + 4B = 3n+6
$$

...

Partikulární řešení:

$$
a_n^p = n+2
$$

$$
a_n = n+2 + 2^n\left(L_1  \cos\left(\frac{\pi n}{3}\right) + L_2 \sin\left(\frac{\pi n}{3}\right)\right)
$$

Dosazení počátečních podmínek:
- $a_0 = 3 = 2L_1$
- $a_1 = 4+\sqrt{3} = 1 + 2 + 2L_1 + 2L_2$

### Řešení
$$
L_1 = L_2 = 1
$$

## Příklad
Nalezněte řešení rekurentního vztahu:
$$
2^{a_{n+2}}*2^{a_{n}} = 14*4^{a_{n+1}}
$$
- $a_0 = 2$
- $a_1 = 4$

### Postup
- [[Logaritmus]]

- $log_2()$
- $16 = 2^4$
- $4 = 2^2$
$$
a_{n+2} + a_n = 4 + 2a_{n+1}
$$

$$
a_{n+2} - 2a_{n+1} + a_n = 4 
$$

Charakteristický polynom:
$$
x^2 - 2x + 1 = 0
$$

$$
(x-1)^2 = 0
$$

Kořen:
- $x_1 = 1$
- $x_2 = 1$

Zkušební řešení:
- $4$ je konstanta
$$
t_n = A
$$

- $A -> L = 0$
- $An -> K = 0$

$$
t_n = An^2
$$

Homogenní řešení:
$$
a_n^h = K + 2n
$$
- Kořeny jsou 1.

Partikulární řešení:
$$
a_n^p = A(n+2)^2 + 2A(n+1)^2 + An^2 = 4
$$

- $A = 2$

Dosazení počátečních podmínek:
$$a_n = 2n^2 + K_2 n + K_1$$
- $a_0 = 2 = K_1$
- $a_1 = 4 = 2+K_2 + K_1$

### Řešení
$$
a_n = 2_n^2+2
$$

