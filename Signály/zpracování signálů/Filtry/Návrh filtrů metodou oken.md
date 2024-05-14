### Metoda oken
> [!info] IRT - Impulse Response Truncation

Navrhujeme pásmovou propust s lineární fází (zpoždění poloviny řádu filtrů).

Myšlenka:
1. Navrhneme ideální filtr ve frekvenční oblasti.
2. Pomocí IDFT získáme impulsní odezvu v časové oblasti.

IDTFT:
$$
x[n] = \frac{1}{2\pi} \int_{-\pi}^{\pi} 
X(e^{j\omega})e^{j\omega n}d\omega
$$

$$
h_{BP}[n] = 
\frac{\omega_2}{\pi} sinc\left[\frac{\omega_2 (n-0.5N)}{\pi} \right] - 
\frac{\omega_1}{\pi} sinc\left[\frac{\omega_1 (n-0.5N)}{\pi} \right] 
$$

- $sinc(x) = \frac{sin(x)}{x}$

Funguje jen na signály u kterých známe všechny vzorky!

Potřebujeme filtry, který reguje jen na omezený počet vzorků.
-> Ořízneme ocásky - okénkovací funkce.
Nechceme IIR, ale FIR!
-> Posuneme doleva o $n$-vzorků.

Použijeme okénkovací funkci:

Teorém o násobení:
$$
h[n] = h_0[n] * w_r[n]
$$
- $w_r[n]$ - okénková funkce

$$
H(e^{j\omega}) = \frac{1}{2\pi}H_0(e^{j\omega})W_r(e^{j\omega})
$$
- $W_r(e^{j\omega})$ - Dirichletův kernel

Okenkovací funkce nám omezí počet vzorků, které potřebujeme znát pro vypočet filtru.

Použití okénkovací funkce však způsobí změny ve frekvenční oblasti oproti ideálnímu filtru.

> [!info]
>Hlavní laloky ovlivní:
>- Velikost přechodového pásma.

> [!info]
>Vedlejší laloky ovlivní:
>- Zvlnění v propustném pásmu,
>- Zvlnění v závěrném pásmu.

Metoda oken:
- [[Návrh filtrů FIR příklady]]