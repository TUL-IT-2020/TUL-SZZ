# Hornerovo schéma
Výpočet hodnoty polynomu v bodě.

$$
(((a_{n-1}x +a_{n-2})x +a_{n-3})x + ... +a_{1})x +a_{0}
$$
Pro výpočet je potřeba jen $n$ součinu a $n$ součtů.

Výpočet tabulkou:

| $b$ | $a_n$ | $a_{n-1}$ | $a_{n-2}$ | ... | $a_{1}$ | $a_{0}$ |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- |
|  | / | $b*a_n$ |  |  |  |  |
|  | $a_n$ | $b*a_n+a_{n-1}$ |  |  |  | $f(b)$ |
Koeficient po dělení f(x) členem (x-b)
## Příklady
[[Hornerovo schéma příklad]]