# Digitální frekvence 

$F_s = 1/T_s$
$$
\omega_k = \frac{2\pi k}{N}
$$
$$
\omega = \frac{2\pi F}{F_s}
$$

$$
\frac{2\pi*F}{F_s} = \frac{2\pi*k}{N}
$$

$\frac{F}{F_s} = \frac{k}{N}$
$k = \frac{FN}{F_s}=F N T_s$

## Příklad
Spojitý signál byl vzorkován se vzorkovací periodou: $T_s = 62,5\mu s$
1. Z prvních 640 vzorků je spočtena DFT, určete index $k$ spektrální komponenty $X[k]$ odpovídající frekvenci 725 Hz.
2. Vektor prvních 640-ti vzorků signálu doplníme o 80 nul, z výsledného vektoru vypočteme DFT. Určete frekvenci $f_k[Hz]$ odpovídající digitální kruhové frekvenci $\omega_k = \frac{\pi}{10}$.

### Postup
1)
$F_s = 16kHz$
N = 640
f = 725Hz

$k = FNT_s$

$k = 29$

2)
N = 720
$f_k = ?$
$\omega_k = \pi/10$

$k = \frac{\omega_k N}{2\pi}$
$k = 36$
$f_k = \frac{k}{N T_s}$
$f_k = \frac{k F_s}{N}$

$f_k = 800$
### Řešení
$k = 29$
$f_k = 800$

## Příklad
Spojitý signál byl vzorkován se vzorkovací periodou: $T_s = 125 µs$. 
1. Z prvních 640 vzorků je spočtena DFT, určete index $k$ spektrální komponenty $X[n]$ odpovídající frekvenci $300 Hz$.
2. Vektor prvních 640-ti vzorků signálu doplníme o 80 nul, z výsledného vektoru vypočítáme DTF. Určete frekvenci $f_k[Hz]$ odpovídající digitální kruhové frekvenci $\omega_k = \frac{\pi}{8}$.
### Postup
$k = FNT_s$
$k = 24$

N = 720
$\omega_k = \pi/8$
$k = \frac{\omega N}{2\pi}$
$k = 45$
$F_k = k *F_S/N$
$F_k = 500$
### Řešení
$k = 24$
$F_k = 500$