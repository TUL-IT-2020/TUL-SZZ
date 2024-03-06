# Filtry FIR
## Klouzavý průměr
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
H(e^{j\omega}) = \frac{1}{3}(1 + e^{-j\omega} + e^{-j2\omega})
$$
