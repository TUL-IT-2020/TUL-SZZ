# Vzorkování
## Příklad
### Zadání
- $x(t) = sin(2\pi 70t)$
- $F_s = 100Hz$

$nT_s = 70t$
### Postup:
$x[n] = sin(2\pi 70* n/100)$
$= sin(1,4\pi n)$ - odečteme $2\pi$
$= sin(-0.6\pi n)$
$= -sin(0.6\pi n)$

$0.6 = \frac{2\pi *F}{100}$

$100-70 = 30$
### Řešení
Aliasing: $30$Hz