# Diskrétní Fourierova transformace - DFT
DFT je diskrétní verze Fourierovy transformace. Diskrétní znamená, že se počítá pouze konečný(nespojitý) počet harmonických složek, tj. konečný počet koeficientů. DFT je výpočetně náročná, proto se používá algoritmus [[FFT - Fast Fourier Transform|FFT]] (Fast Fourier Transform), který je výpočetně efektivnější.

## Předpis
> [!important]
$$
X[k] = \frac{1}{N} \sum_{n=0}^{N-1} x[n] e^{-j k \frac{2 \pi}{N} n}
$$

> [!example]
- $x[n]$ je vzorek signálu
- $X[k]$ je komplexní koeficient
	- $k$ je index koeficientu
- $0 \leq k \leq N-1$
	- $k$ - index frekvence
	- $n$ - index vzorku
	- $N$ - počet vzorků signálu

- $\omega = \frac{2\pi}{N}k$ - [[Digitální frekvence|digitální frekvence]]

## Složitost: 
$O(N^2)$

## Použití
- DFT se používá pro analýzu diskrétních signálů
- výsledkem je **frekvenční spektrum signálu**, které obsahuje informace o frekvencích a amplitudách harmonických složek signálu

## FFT - Fast Fourier Transform
![[FFT - Fast Fourier Transform]]

## Příklady
![[DTF příklady]]