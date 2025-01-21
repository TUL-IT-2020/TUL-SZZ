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
### Postup

### Řešení