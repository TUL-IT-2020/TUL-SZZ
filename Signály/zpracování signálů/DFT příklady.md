# DFT
> [!important]
$$
X[k] = \sum_{n=0}^{N-1} x[n]e^{−j2πnk/N}
$$
- $0 ≤ k ≤ N − 1$

- [[Goniometrie]]

Hodí se znát Eulerova notace:
![[Komplexní exponenciála]]
## Příklad:
$$x[n] = \delta[n-0] - 2\delta[n-1] + 4\delta[n-3]$$
$X[k] = ?$

- $N = 4$

### Postup:
- $k = 0$
- $\omega_0 = \frac{2\pi*1*0}{4} = 0$
$$
x[0] = 1* e^{-j\frac{2\pi*0*0}{4}} 
- 2 * e^{-j\frac{2\pi*0*1}{4}} 
+ 4 * e^{-j\frac{2\pi*0*3}{4}} 
+ = 1 - 2 + 4 = 3
$$

- $k = 1$
- $\omega_1 = \frac{2\pi*1*1}{4} = \pi/2$
$$
x[1] = 1* e^{-j\frac{2\pi*1*0}{4}} 
- 2 * e^{-j\frac{2\pi*1*1}{4}} 
+ 4 * e^{-j\frac{2\pi*1*3}{4}} 
+ = 1 + 2j +4j = 1+6j
$$

$e^{-j\pi/2} = -j$
$e^{-j\pi*3/4} = +j$

- $k = 2$
- $\omega_2 = \frac{2\pi*1*2}{4} = \pi$
...

## Příklad
$$
x[n] = 0.5δ[n] + 1.5δ[n − 1] + 2.5δ[n − 3].
$$
- $N = 4, n = 0 . . . 3$

- $N = 4$
- $k = 0$
$X[0] = 0.5e^{-j2\pi0\cdot 0/4} + 1.5e^{-j1\pi2\cdot 0/4} + 2.5e^{-j2\pi3\cdot 0/4}$
$X[0] = 0.5e^0 + 1.5e^0 + 2.5e^0 = 4,5$

- $k = 1$
$X[1] = 0.5e^{-j2\pi0\cdot 1/4} + 1.5e^{-j2\pi1\cdot 1/4} + 2.5e^{-j2\pi3\cdot 1/4}$
$X[1] = 0.5e^0 + 1.5e^{-j\pi1/2} + 2.5e^{-j\pi3/2}$
$X[1] = 0.5 + 1.5(-j) + 2.5(+j) = 0.5 + j$

- $k = 2$
$X[2] = 0.5e^{-j2\pi0\cdot 2/4} + 1.5e^{-j2\pi1\cdot 2/4} + 2.5e^{-j2\pi3\cdot 2/4}$
$X[2] = 0.5 + 1.5e^{-j\pi} + 2.5e^{-j3\pi}$
$X[2] = 0.5 + 1.5(-1) + 2.5(-1) = -3.5$

- $k = 3$
$X[3] = 0.5e^{-j2\pi0\cdot 3/4} + 1.5e^{-j2\pi1\cdot 3/4} + 2.5e^{-j2\pi3\cdot 3/4}$
$X[3] = 0.5 + 1.5e^{-j2\pi 3/4} + 2.5e^{-j2\pi3\cdot 3/4}$
$X[3] = 0.5 + 1.5(j) + 2.5(-1) = 0.5 -j$

Indexy: $k ∈ (0, 1, 2, 3)$, odpovídají frekvenci: $ω_k \in \{0, 1/2π, π, 3/2π \}$

$$
\omega_k = \frac{2\pi k}{N}
$$
$$
\omega_k = \frac{\pi k}{2}
$$
