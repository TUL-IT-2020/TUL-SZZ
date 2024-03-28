# Aliasing
## Příklad vzorkování frekvence

$$
\omega = \frac{2\pi f}{F_s}
$$

- $F_s = 16kHz$
- $F = 4kHz$

$\omega = 1/2 \pi$

- $F = -4kHz$

$\omega = -1/2 \pi$

$sin(-1/2 \pi) = -sin(1/2 \pi)$

- signál je v protifázi
## Příklad
$x(t) = sin(2*\pi*80*t)$
- $F_s = 100Hz$

$sin(2*\pi*80*n/100) =sin(1/6*\pi*n)$ 
- odečteme $2\pi$, aby jsme se vrátili do základního spektra.
$= sin(-0.4*\pi*n)$
$= -sin(0.4*\pi*n)$

Aliasingem se nám signál přeloží na: $-20Hz$
Bude tedy mít zápornou fázi a frekvenci $20Hz$.
