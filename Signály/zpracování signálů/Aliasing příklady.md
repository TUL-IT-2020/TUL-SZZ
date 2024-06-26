#příklad 
# Aliasing

$$
\omega = \frac{2\pi f}{F_s}
$$
## Příklad vzorkování frekvence
- $F_s = 16kHz$
- $F = 4kHz$

Po dosazení do vzorce, získáme digitální frekvenci:
$\omega = 1/2 \pi$

Signál o frekvenci:
- $F = -4kHz$

$\omega = -1/2 \pi$

$sin(-1/2 \pi) = -sin(1/2 \pi)$

- signál je v protifázi

## Příklad vzorkování frekvence
- $x(t) = sin(2\pi 70t)$
- $F_s = 100Hz$

$nT_s = 70t$
### Postup:
$x[n] = sin(2\pi 70* n/100)$
$= sin(1,4\pi n)$ - odečteme $2\pi$
$= sin(-0.6\pi n)$
$= -sin(0.6\pi n)$

Dosadíme do vzorce pro digitální frekvenci:
- $0.6\pi = \frac{2\pi *F}{100}$
Upravíme:
- $F = 0.6*100/2 = 30$

Nebo:
$70-100 = -30$
### Řešení:
Aliasing: $30$Hz

## Příklad
$x(t) = sin(2*\pi*80*t)$
- $F_s = 100Hz$
### Postup:
$sin(2*\pi*80*n/100) =sin(1/6*\pi*n)$ 
- odečteme $2\pi$, aby jsme se vrátili do základního spektra.
$= sin(-0.4*\pi*n)$
$= -sin(0.4*\pi*n)$
### Řešení:
Aliasingem se nám signál přeloží na: $-20Hz$
Bude tedy mít zápornou fázi a frekvenci $20Hz$.
