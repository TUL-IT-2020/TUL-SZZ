### Metoda nejmenších čtverců
> [!info] LSE

Minimalize chyby numericky za pomoci optimalizace.
Lepší výsledky než metoda oken. 

Optimalizujeme parametr $B$.

$$
\epsilon^2 = \int_{0}^{\pi} 
\left(V(\omega)[A_d(\omega) - A(\omega)]\right)^2d\omega
$$

- $A_d$ - desired
- $V$ - váhy
  - malé číslo velká váha

Matlab:
```matlab
firls(N, f, a, w)
```
- `N` - řád filtru
- `f` - frekvence
- `a` - amplituda
- `w` - váhy

```matlab
% HP
% lse
% zadane hodnoty
wp = 0.8*pi;
ws = 0.7*pi;
dp = 1e-3;
ds = 2e-4;

% nastaveni parametru
L = 121;
N = L-1;
F = [0 wp ws 1];
A = [0 0 1 1];
W = [1/dp 1/ds];

% navrh filtru
h = firls(N, F, A, W);

% frekvencni charakteristika
[H, w] = freqz(h, 1, 1000);
figure;
plot(w/pi, abs(H));
title('Frekvenční charakteristika filtru');
```