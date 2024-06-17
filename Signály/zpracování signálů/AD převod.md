# A/D převod
- vzorkování
- kvantování

![[Sampling-Analog-Signal-2.jpg]]

[[AD převodníky]]
## Vzorkování
Vzorkovací frekvence:
- $F_s [Hz]$ - jednotkou Herz

- $X_a(t)$ - analogový signál (analog signal)
- $X_s(t)$ - vzorkovaný signál (sampled signal)
- $t$ - čas, spojitý 

### V časové oblasti:
1) Násobení hřebenovým pulzem:
$$X_s(t) = X_a(t) * t_a(t)$$
2) Vzorkování:
$$x[n] = x_s(nT_s)$$

### Ve frekvenční oblasti:
1) 
$$X_s(\Omega) = 1/2\pi X_a(\Omega) * S_a(\Omega)$$
2) $F_S$ krát se zmenší spektrum

$\omega = \Omega*T_s = 2\pi*F*T_S=\frac{2\pi*F}{T}$

### Trojúhelníky ve spektru
- $\Omega = 2\pi*F$
- $X(\Omega)$

> [!warning] 
> Aby se trojuhelníky nepřekrývaly, tak $F_S$ musí být alespoň dvojnásobek nejvyšší frekvence.

> [!info] Jinak vzniká aliasing. 
> "Alias" - překrytí nižších frekvencí.

> [!tip]
> Řešení se dolní propustí na stupu A/D převodníku. A vzorkováním na výrazně vyšší frekvenci (oversampling).

### Příklady
![[Aliasing příklady]]
## Kvantování

### Poměr kvantování a šumu
Každých 6 bitů se zvětší rozsah o 1dB.

## Převzorkování
![[Převzorkování]]