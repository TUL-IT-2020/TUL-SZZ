#příklad 
# Řešení diferenční rovnice s počátečními podmínkami
- Numerické řešení filtrů, -> vektor hodnot
- Analitické řešení. -> funkce

## Postup
DTFT:
Impulzní odezva:
- $H(e^{j\omega}) = ?$
Pak dosadíme $x$:
Parciální zlomky:
- Substituce:
	- $e^{-j\omega} = x$
- Kvadratická rovnice:
- Zpětně dosadíme:
	- $x = e^{-j\omega}$
IDTFT:
Dopočítáme odezvu
## Příklad
Určete odezvu kauzálního systému popsaného diferenční rovnicí:
$$
y[n] = 0.5y[n − 1] + x[n]
$$
na jednotkový skok $u[n]$, jsou-li dány počáteční podmínky:
- $y[-1] = 1/4$, 
- $y[-2] = 1$.

### Postup

$H(e^{j\omega}) = ?$

$$
Y(e^{j\omega}) = 1/2Y(e^{j\omega})e^{-j\omega} + X(e^{j\omega})
$$
$$
Y(e^{j\omega})- 1/2Y(e^{j\omega})e^{-j\omega} = X(e^{j\omega})
$$
$$
Y(e^{j\omega})(1- 1/2e^{-j\omega}) = X(e^{j\omega})
$$
Impulzní odezva:
$$
H(e^{j\omega}) 
= \frac{Y(e^{j\omega})}{X(e^{j\omega}) }
= \frac{1}{1- 1/2e^{-j\omega}}
$$

### Řešení
## Příklad
Určete odezvu systému popsaného diferenční rovnicí:
$$
y[𝑛] = \frac{3}{4} 𝑦[𝑛 −1] -\frac{1}{8}𝑦[𝑛 −2] +x[n]
$$
Na vstupní signál $𝑥[𝑛] = 𝛿[𝑛]$, jsou-li počáteční podmínky:
- $𝑦[−1] = −1$,
- $𝑦[−2] = 1$.

### Postup

DTFT:
$$
Y(e^{j\omega}) = \frac{3}{4} Y(e^{j\omega})e^{-j\omega} -\frac{1}{8}Y(e^{j\omega})e^{-j2\omega} + X(e^{j\omega})
$$
$$
Y(e^{j\omega}) - \frac{3}{4} Y(e^{j\omega})e^{-j\omega} +\frac{1}{8}Y(e^{j\omega})e^{-j2\omega} = X(e^{j\omega})
$$
$$
Y(e^{j\omega})\left(1 - \frac{3}{4}e^{-j\omega} +\frac{1}{8}e^{-j2\omega} \right) = X(e^{j\omega})
$$
Impulzní odezva:
$H(e^{j\omega}) = ?$
$$
H(e^{j\omega}) 
= \frac{Y(e^{j\omega})}{X(e^{j\omega})}
= \frac{1}{1 - \frac{3}{4}e^{-j\omega} +\frac{1}{8}e^{-j2\omega}}
$$
$x$ se rovná:
- $x=(1)$
Tak ho dosadíme:
$$
Y(e^{j\omega})= \frac{1}{1 - \frac{3}{4}e^{-j\omega} +\frac{1}{8}e^{-j2\omega}}
$$
Parciální zlomky:
- [[Parciální zlomky]]
$$
Y(e^{j\omega})= 
\frac{A}{1 - \frac{3}{4}e^{-j\omega}} + 
\frac{B}{\frac{1}{8}e^{-j2\omega}}
$$
Substituce:
- $e^{-j\omega} = x$
$$
1 - \frac{3}{4}x +\frac{1}{8}x^2
$$
Kvadratická rovnice:
- [[Kvadratická rovnice]]

Co na to wolfram?
```Wolfram
partial fractions 1/(1-3/4x+1/8x^2)
```
$$
\frac{4}{x-4} - \frac{4}{x-2}
$$
Zpětně dosadíme:
$$
Y(e^{j\omega})= \frac{-1}{1-1/4e^{-j\omega}} + \frac{2}{1-1/2e^{-j\omega}}
$$
### Řešení

## Příklad
Určete odezvu systému popsaného diferenční rovnicí:
$$
y[n] = \frac{3}{4} · y[n − 1] − \frac{1}{8} · y[n − 2] + x[n] − x[n − 1]
$$
Na vstupní signál $𝑥[𝑛] = 𝛿[𝑛]$, jsou-li počáteční podmínky:
- $𝑦[−1] = 0$,
- $𝑦[−2] = 0$.
### Postup

$H(e^{j\omega}) = ?$
$$
Y(e^{j\omega}) = \frac{3}{4} · Y(e^{j\omega})e^{-j\omega} − \frac{1}{8} · Y(e^{j\omega})e^{-j2\omega} + X(e^{j\omega}) − X(e^{j\omega})e^{-j\omega}
$$
$$
Y(e^{j\omega}) - \frac{3}{4} · Y(e^{j\omega})e^{-j\omega} + \frac{1}{8} · Y(e^{j\omega})e^{-j2\omega} 
=  X(e^{j\omega}) − X(e^{j\omega})e^{-j\omega}
$$
$$
Y(e^{j\omega}) \left(1- \frac{3}{4}e^{-j\omega} + \frac{1}{8}e^{-j2\omega}\right) 
=  X(e^{j\omega})\left(1 − e^{-j\omega}\right) 
$$
### Řešení
$$
H(e^{j\omega}) 
= \frac{Y(e^{j\omega})}{X(e^{j\omega})}
= \frac{1 − e^{-j\omega}}{1- \frac{3}{4}e^{-j\omega} + \frac{1}{8}e^{-j2\omega}} 
$$
