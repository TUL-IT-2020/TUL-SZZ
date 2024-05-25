# DTFT spektrum
Furieorova transformace v diskrétním čase.
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
Dirichletův kernel -> okénko pro výběr omezené části signálu, přidává nám laloky.
- $W_r$ - Dirichletův kernel 
- $\frac{4\pi}{N}$ - šířka laloku

> [!warning] Je těžké objevit komponenty, které jsou:
>- Blízké -> splynutí laloků -> chceme úzký hlavní lalok
>- Slabé -> překrytí laloků -> chceme malé vedlejší laloky

Kompromis mezi šířkou hlavního laloku a velikostí vedlejších laloků.

> [!Example] Okénkovací funkce:
>- obdélníkové
>- trojúhelníkové
>- Hamming
>- Blackmann
>- Kaiser - je parametrické
