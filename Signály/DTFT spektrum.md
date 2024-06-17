# DTFT spektrum
Discrete time Fourier transform - Fourierova transformace v diskrétním čase.
## Spektrogram
3D graf, vzniklý spojením DFT za sebe.
Okýnka se překrývají pro větší časové rozlišení.

Snažíme se získat bločky stacionárních signálů. Čím delší blok, tím větší rozlišení.

Konečný výběr signálu:

$$
x[n] = y[n] \times w_r[n]
$$
DTFT:
$$
X(e^{j\omega}) = \frac{1}{2\pi} Y(e^{j\omega}) * W_r(e^{j\omega})
$$

![[Okénkovací funkce]]