# DFT:
$$
X[k] = \sum_{n=0}^{N-1} x[n]e^{-j\frac{2\pi*kn}{N}}
$$
- $\omega = \frac{2\pi}{N}k$ - digitální frekvence
- $0 \leq k \leq N-1$
- $k$ - index frekvence
- $n$ - index vzorku
- $N$ - počet vzorků

Složitost: $O(N^2)$

## Příklady
![[DTF příklady]]