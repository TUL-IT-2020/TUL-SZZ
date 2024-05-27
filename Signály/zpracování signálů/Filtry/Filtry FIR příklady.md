# Filtry FIR
- [[Tabulka DTFT párů]]
## Klouzavý průměr
- [[Klouzavý průměr]]
Pro 3 hodnoty:

$$
Y[n] = \frac{1}{3} \cdot (X[n] + X[n-1] + X[n-2])
$$
- $x[n] = \delta[n]$
### Postup
$$
h[n] = \frac{1}{3}(\delta[n] + \delta[n-1] + \delta[n-2])
$$

Frekvenční charakteristika:
$$
H(e^{j\omega}) = \frac{Y(e^{j\omega})}{X(e^{j\omega})}
$$

$$
H(e^{j\omega})_{\omega=\pi/2} = \frac{1}{3}(1 + e^{-j\omega} + e^{-j2\omega})
$$
- $1 -j -1 = -j$
- $H = \frac{-j}{3}$

Magnituda:
$$
|H(e^{j\omega})| = \frac{-1}{3}
$$

Fáze:
$$
\phi(e^{j\omega}) = -\frac{\pi}{2}
$$

Zpoždění:
$$
\tau_p = \frac{\phi(\omega)}{\omega} = -\frac{-\pi/2}{\pi/2} = 1
$$
- $\omega = \pi/2$

Zpoždění je 1 vzorek.

### Vlastní funkce (cos)
$x[n] = cos(u \pi/2)$

$y[n] = 1/3 \cdot (cos(u \pi/2)$

$y[n] = 1/3 \cdot cos(\pi/2 (n-1))$