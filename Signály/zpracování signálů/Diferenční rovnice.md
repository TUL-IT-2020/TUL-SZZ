# Diferenční rovnice
> [!important]
$$
y[n] = \sum_{k=0}^q b[k]x[n-k] - \sum_{k=1}^p a[k]y[n-k]
$$
- $a$ - koeficienty $y$
- $b$ - koeficienty $x$

> [!note]
> Druhá suma začíná na index $1$ jelikož $0$ člen je na levé straně rovnice.
> Obdobně druhou lineární kombinaci odčítáme od té první protože jsme ji přesunuli z leva.  

Diferenční rovnice -> výstup z filtru
1. Numerická (Dosadíme za $n$, `filter`)
2. Analytická (DFT, teorém o posunutí, `conv`, `filter`)

>[!tip] Teorém o posunutí
$x[n] -> X(e^{j\omega})$
$x[n-n_0] -> X(e^{j\omega})*e^{-j\omega n_0}$

>[!example]
$X(e^{j\omega})$
>- $\omega \in R [-]$ - [[Digitální frekvence|digitální frekvence]], $\omega \in (0, \pi)$
>- $f \in R [Hz]$ - [[Analogová frekvence|analogová frekvence]]
>
>$\omega = 2\pi*\frac{F}{F_s}$ 
>- $\omega = \pi$
>
>$F = F_s/2$

## Příklady:
- [[Diferenční rovnice příklady]]