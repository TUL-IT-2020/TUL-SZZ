# Filtrace
## Různé vlastnosti filtrů:

### Stabilní filtr
Pro omezený vstup má omezený výstup.

### Kauzální filtr
Musí mít odezvu směrem doprava. Tedy když nepotřebuje žádné vzorky z budoucnosti!

Například: 
![[Klouzavý průměr]]

### Filtry s lineární fází 
> [!tip] Filtry s lineární fází 
> Neupravují signál, pouze jej posouvají v čase.
## Metody popisu filtru:
- diferenční rovnicí
- v časové oblasti
- ve frekvenční oblasti 

> [!tip]
V časové oblasti: konvoluce, ve frekvenční násobení.

Diferenční rovnice -> výstup z filtru
1. Numerická (Dosadíme za $n$, `filter`)
2. Analytická (DFT, teorém o posunutí, `conv`, `filter`)

>[!tip] Teorém o posunutí
$x[n] -> X(e^{j\omega})$
$x[n-n_0] -> X(e^{j\omega})*e^{-j\omega n_0}$

### V časové oblasti pomocí konvoluce:
$$
y[n] = \sum_{k=-\infty}^{\infty} h[k]x[n-k]
$$

### Ve [[Furierova transformace|frekvenční]] oblasti:
$$
Y(e^{j\omega}) = H(e^{j\omega})X(e^{j\omega})
$$

### V [[Z-transformace|Z]] oblasti:
$$
Y(z) = H(z)X(z)
$$

## Typy filtrů
- [[FIR - Finite Impulse Response]]
- [[IIR - Infinite Impulse Response]]

### FIR
Lze realizovat za pomoci konvoluce.
- [[Filtry FIR příklady]]
### IIR
- [[Filtry IIR příklady]]

## Inverzní filtr
$$
x[n] * h[n] * g[n] = x[n] = x[n] * \delta[n]
$$

$$
h[n] * g[n] = \delta[n]
$$

### Ve frekvenční oblasti:
$$
H(e^{j\omega})G(e^{j\omega}) = 1
$$

$$
G(e^{j\omega}) = \frac{1}{H(e^{j\omega})}
$$
> [!warning]
> Nemá smysl pro $H = 0$, tedy tam kde se nám frekvence nulují.

> [!tip]
> V praxi nám stačí prohodit koeficienty `A` a `B`, při tvorbě filtru.

> [!info]
> K FIR je inverzní k IIR a naopak.

## Příklady filtrů

Allpass filter
- pracuje jen s fází

### Frekvenčně selektivní filtry
> [!example] Frekvenčně selektivní filtry
>- Dolní propust
>- Pásmová propust
>- Pásmová zádrž
>- Horní propust

### Filtry s lineární fází
Impulzní odezva musí být:
- konečná,
- sudě symetrická.

Když filtr propouští signál, tak mu nic nedělá.

## Spojení filtrů
![[Spojení filtrů]]

## Decibely
![[Decibely]]



