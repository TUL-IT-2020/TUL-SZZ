# Vzorkování
> [!note] 
> Vzorkování, kvantování. Vzorkovací teorém. Aliasing. Práce se zvukem na počítači.

$$
x(t) = A cos(2 \pi ft) \quad \text{spojitá cosinusovka}
$$
- $A$ je amplituda
- $f$ je frekvence
- $t$ je čas
- $2 \pi f t$ je fázový posun

$$
x[n] = A cos(2 \pi f n T_s) = A cos(2 \pi n \frac{f}{f_s}) \quad \text{diskrétní cosinusovka}
$$

## Aliasing
- překládání frekvencí
- jev, kdy se vznikají nové frekvence, které nejsou ve vzorkovaném signálu obsaženy
### Shannonův (Nyquistův) Vzorkovací teorém
- Nemá li dojít při vzorkování analogových signálů ke ztrátě či ke zkreslení informace, musí být vzorkovací frekvence alespoň dvojnásobkem nejvyšší frekvence obsažené v signálu.
### Příklady
[[Aliasing příklady]]
## Převzorkování signálu
![[Převzorkování]]
## Příklady
![[Vzorkování příklady]]