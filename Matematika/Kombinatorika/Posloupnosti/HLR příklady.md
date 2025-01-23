# HLR

## Příklad: Fibonaci

1) Obecné řešení rovnice
2) Počáteční podmínky

$$
F_{n+2} = F_{n+1} + F_n
$$

- $(F_0 = 0, F_1 = 1)$

### Postup
Řešení: hledáme ve tvaru diskrétní exponenciály.

$r^n, n \in N$

->
$$
r^{n+2} -r^{n+1} -r^{n}  = 0
$$
$$
r^n(r^2-r-1)=0
$$

Kvadratická rovnice:

...
Kořeny:
$$
\frac{1+\sqrt{5}}{2};\frac{1-\sqrt{5}}{2}
$$
Počáteční podmínky:
$$
F_n = K(\frac{1+\sqrt{5}}{2}) + L(\frac{1-\sqrt{5}}{2})
$$
$$
F_n = \frac{1}{\sqrt{5}}
\left[
\left(\frac{1+\sqrt{5}}{2}\right)-
\left(\frac{1+\sqrt{5}}{2}\right)
\right]
$$
Done

## Příklad

$$
4 a_n + 4a_{n+1} + a_{n+2} = 0
$$
- $a_0 = 0$
- $a_1 = -2$

1) Obecné řešení?
2) PP řešení?

### Postup
Členy $a_n$ nahradíme za $r^n$ a získáme ta charakteristickou rovnici:
$$
4r^n+4r^{n+1}+r^{n+2}=0
$$
Vytkneme $r^n$:
$$
r^2+4r+4=0
$$
Tato kvadratická rovnice má kořeny:
$r=−2$
(dvojnásobný kořen)

Obecné řešení:
$$
a_n​=C_1​(−2)^n+​nC_{2}(−2)^n
$$
kde :
- $-2$ - kořen,
- $n*C_2$ - protože proč ne když je to vícenásobný kořen,
- $C_1$​ a $C_2$​ jsou neznámé konstanty, které určíme z počátečních podmínek.

Použijeme počáteční podmínky:

1. Pro n=0:
$$
a_0=C_1(−2)^0+C_2(0)(−2)^0=C_1=0.
$$
- $C1=0$

2. Pro n=1:
$$
a_1=C_1(−2)^1+C_2(1)(−2)^1=0
$$
Protože $a_1 = -2$, máme:
$$
-2C_2 = -2 \implies C_2 = 1
$$
Partikulární řešení:
$$
a_n​=n(−2)^n
$$
### Řešení
Obecné řešení:
$$
a_n​=C_1​(−2)^n+​nC_{2}(−2)^n
$$
Partikulární:
$$
a_n​=n(−2)^n
$$

## Příklad: komplexní kořeny
$$
a_{n+4} + 3a_{n+2} - 4a_n = 0
$$
- $a_0 = 6$
- $a_1 = 7$
- $a_2 = -9$
- $a_3 = -33$
### Postup

char. polynom:
$$
x^4+3x^2-4=0
$$
- $x_1 = 1$
- $x_2 = -1$
$$
(x-1)(x+1)(x^2+4)=0
$$

$(x^2+4)$ má kořeny:
- $x_3 = 2i$,
- $x_4 = -2i$

Obecné řešení:
$$
a_n = C_1(1)^n + C_2(-1)^n + C_3(2i)^n + C_4(-2i)^n
$$

$$
\pm 2i = 2(\cos \frac{\pi}{2} + i \sin \frac{\pi}{2})
$$
$$
(\pm 2i)^n = 2^n(\cos \frac{n\pi}{2} + i \sin \frac{n\pi}{2})
$$

$$
a_n = C_1 + C_2(-1)^n + C_3*2^n\cos \frac{n\pi}{2} + C_4*2^n\sin \frac{n\pi}{2}
$$

Počáteční podmínky:
$$
a_0 = 6 = C_1 + C_2 + 1C_3\cos(0) + 1C_4*2*0
$$
$$
a_1 = 7 = C_1 - C_2 + 0 + 2C_4
$$
$$
a_2 = -9 = C_1 + C_2 - 4C_3 + 0
$$
$$
a_3 = -33 = C_1 - C_2 - 0 - 8C_4
$$

GEM:
$$
\begin{bmatrix}
1 & 1 & 1 & 0 & 6 \\
1 & -1 & 0 & 2 & 7 \\
1 & 1 & -4 & 0 & -9 \\
1 & -1 & 0 & -8 & -33
\end{bmatrix}
$$
### Řešení


## Příklad
$$
\Delta^2 a_n + 2\Delta a_n = a_n  
$$

- $a_{10} = ?$
- $a_1 = 5\sqrt{2}$

### Postup

$$
\Delta a_n = a_{n+1} - a_n
$$
$$
\Delta^{(2)} a_n = a_{n+2} -2a_{n+1} + a_n
$$
Rekurentní vztah:
$$
a_n = a_{n+2} -2a_{n+1} + a_n + 2(a_{n+1} - a_n)
$$
$$
a_n = a_{n+2} - a_n
$$
$$
a_{n+2} - 2a_n = 0
$$

Charakteristický polynom:
$$
x^2 - 2 = 0	
$$

Kořeny:
- $x_1 = \sqrt{2}$
- $x_2 = -\sqrt{2}$

Obecné řešení:
$$
a_n = C_1 (\sqrt{2})^n + C_2 (-\sqrt{2})^n
$$

Použijeme počáteční podmínky:
- $a_1 = 5\sqrt{2} = C_1 \sqrt{2} - C_2 \sqrt{2}$

$$
5 = C_1 - C_2
$$

- $K = 5 + C_2$

???

$$
a_n = (5 + K)(\sqrt{2})^n + K (-\sqrt{2})^n
$$

???

$$
a_n = 2^{n/2}(5+2K)
$$

$2^5 = 32$

### Řešení
$$
a_{10} = 32(5+2K)
$$
Nekonečně mnoho posloupností.


## Příklad
Vyřešte rekurentní vztah:
$$
a_{n+3} + 3a_{n+2} - 4a_n = 0
$$

- $a_0 = -1$
- $a_1 = 6$
- $a_2 = -2$

### Postup

Charakteristický polynom:
$$
x^3 + 3x^2 - 4 = 0
$$

$$
x^3 + 3x^2 - 4 =(x-1)(x^2 + 4x + 4) = (x-1)(x+2)^2
$$

Kořeny:
- $x_1 = 1$
- $x_2 = -2$
- $x_3 = -2$

Obecné řešení:
$$
a_n = C_1(1)^n + C_2(-2)^n + nC_3(-2)^n
$$
- $nC_3$ - protože $-2$ je kořen násobnosti 2.

Počáteční podmínky:
- $a_0 = -1 = C_1 + C_2$
- $a_1 = 6 = C_1 - 2C_2 - 2C_3$
- $a_2 = -2 = C_1 + 4C_2 - 8C_3$

GEM:
$$
\begin{pmatrix}
1 & 1 & 0 & -1 \\
1 & -2 & -2 & 6 \\
1 & 4 & -8 & -2
\end{pmatrix}
$$

Solved:
$$
\begin{pmatrix}
1 & 0 & 0 & 2 \\
0 & 1 & 0 & -3 \\
0 & 0 & 1 & 1
\end{pmatrix}
$$

Obecné řešení:
$$
a_n = 2 - 3(-2)^n + n(-2)^n
$$

### Řešení
$$
a_n = 2 - 3(-2)^n + n(-2)^n
$$

## Příklad
$$
a_{n+2} + Ba_{n+1} + Ca_n = 0
$$
- $B,C \in R$

Určete $B,C$ tak, aby posloupnost $a_n = K_1 + K_2*7^n$ byla řešením.

### Postup
Kořeny:
$a_n = K_1 + K_2*7^n$

- $x_1 = 1$
- $x_2 = 7$ 

Charakteristický polynom:
$$
x^2 + Bx + C = 0	
$$
->
$$
(x-1)(x-7) = 0
$$

- $B = -8$
- $C = 7$

### Řešení
- $B = -8$
- $C = 7$