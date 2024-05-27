# Filtry IIR
- [[Tabulka DTFT párů]]
## Příklad
Filtr s nekonečnou impulsní odezvou:
$$
y[n] = x[n] + \frac{1}{2}y[n-1]
$$

### Postup:
DTFT:
- Přešli jsme do frekvenční oblasti:
$$
Y(e^{j\omega}) = X(e^{j\omega}) + \frac{1}{2}Y(e^{j\omega})e^{-j\omega}
$$
- $e^{-j\omega}$ - zpoždění o 1 vzorek (aplikace teorému o posunutí v čase)

$$
Y(e^{j\omega})(1 - \frac{1}{2}e^{-j\omega}) = X(e^{j\omega})
$$
- $Y(e^{j\omega})$ - vytkneme, proto: (1-...)
### Řešení
$$
H(e^{j\omega}) = \frac{Y(e^{j\omega})}{X(e^{j\omega})} = \frac{1}{1 - \frac{1}{2}e^{-j\omega}}
$$

## Příklad 

$$
y[n] = \frac{1}{4}y[n-1] + x[n] - x[n-2]
$$
- $x[n] = \delta[n]$

### Postup:
DFTF:
$$
Y(e^{j\omega}) = \frac{1}{4}Y(e^{j\omega})e^{-j\omega} + X(e^{j\omega}) - e^{-j2\omega}X(e^{j\omega})
$$

$$
Y(e^{j\omega})(1 - 1/4e^{-j\omega}) = X(e^{j\omega})(1 - e^{-j2\omega})
$$

### Řešení:
$$
H(e^{j\omega}) = \frac{Y(e^{j\omega})}{X(e^{j\omega})} = \frac{(1 - e^{-j2\omega})}{(1 - 1/4e^{-j\omega})}
$$
## Příklad

$$
h[n] = (1/2)^n \cdot u[n]
$$

- $u[n]$ - jednotková funkce
### Postup:
$$
h[n] = (1/2)^n \cdot u[n]
$$

$$
y[n] = x[n] + \frac{1}{2}y[n-1]
$$

$$
y[n] = x[n] * h[n]
$$
#WTF
DTFT:
$$
Y(e^{j\omega}) = \frac{1}{1 - 1/2 e^{-j\omega}} \cdot \frac{1}{1 - 1/3 e^{-j\omega}}
$$
 
$$
Y(e^{j\omega}) = \frac{A}{(1 - 1/2 e^{-j\omega})} + \frac{B}{(1 - 1/3 e^{-j\omega})}
$$
 
Parciální zlomky:
$$
1 = A(1 - 1/3 e^{-j\omega}) + B(1 - 1/2 e^{-j\omega})
$$

$A + B = 1$
$-1/3A - 1/2B = 0$

- $B = -2$
- $A = 3$  

IDFT:

$$
y[n] = 3 (1/2)^n \cdot u[n] - 2 (1/3)^n \cdot u[n]
$$