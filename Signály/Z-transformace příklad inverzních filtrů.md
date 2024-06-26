# Z-transformace příklad inverzních filtrů
$$
G(z) = \frac{1}{H(z)}
$$
## Příklad
$y[n] = x[n] * h[n]$
- $h[n] = (1/2)^n \mu[n]$

### Postup
$$
H(z) = \frac{1}{1-1/2z^{-1}}
$$
- |z| > 1/2
  
$$
Y(z) = \frac{1}{1-1/2z^{-1}}* \frac{-3z^{-1}}{1-3z^{-1}}
$$

$$
Y(z) = \frac{A}{1-1/2z^{-1}} + \frac{B}{1-3z^{-1}}
$$

Nebo:

$A_k = [(1-\alpha)X(z)]_{z=a_k}$
- $a_k$ jsou póly

A:
$$
Y(z)*(1-1/2z^{-1}) = \frac{-3z^{-1}}{1-3z^{-1}}
$$
- $z = 1/2$
- $z^{-1} = 2$
  
$=6/5$

B:
$$
Y(z)*(1-3z^{-1}) = \frac{-3z^{-1}}{1-1/2z^{-1}}
$$
- $z = 3$
- $z^{-1} = 1/3$

$= -6/5$

$$
Y(z) = \frac{6/5}{1-1/2z^{-1}} - \frac{6/5}{1-3z^{-1}}
$$

### Řešení
$y[n] = \frac{6}{5}(1/2)^n\mu[n] + \frac{6}{5}(3)^n\mu[-n-1]$

## Příklad
$$
X(z) = 4+3z^{2}+3z^{-2}
$$
- $0< |z| < \infty$
### Řešení
$x[n] = 4\delta[n] + 3\delta[n-2] + 3\delta[n+2]$

## Příklad
$$
X(z) = \frac{1}{1-1/2z^{-1}} + \frac{3}{1-1/3z^{-1}}
$$
- $|z| > 1/2$, $|z| > 1/3$

### Řešení
$x[n] = (1/2)^n\mu[n] + 3(1/3)^n\mu[n]$

## Příklad
$$
X(z) = \frac{1}{1+3z^{-1}+2z^{-2}}
$$
- $|z| > 2$

```matlab
b = [1];
a = [1 3 2];
[z,p,k] = residuez(b,a)
```
$$
X(z) = \frac{2}{1+2z^{-1}} + \frac{-1}{1+z^{-1}}
$$

### Řešení
$x[n] = 2(-2)^n\mu[n] - 1(-1)^n\mu[n]$
## Příklad
$$
H(z) = \frac{1-0.5z^{-1}}{1-0.8z^{-1}}
$$
- $|z|>0.8$

### Postup
$$
G(z) = \frac{1-0.8z^{-1}}{1-0.5z^{-1}}
$$
1) $|z|>0.5$, stabilní, [[Kauzalita|kauzální]],
2) $|z|<0.5$, nestabilní, nekauzální

Regiony konvergence musí mít společný průnik.

$|z|>0.5$ je platný.


## Příklad
$$
H(z) = \frac{0.5-z^{-1}}{1-0.8z^{-1}}
$$
- $|z|>0.8$, stabilní

### Postup
$$
G(z) = \frac{1-0.8z^{-1}}{0.5-z^{-1}}
$$

$$
G(z) = 
\frac{1}{0.5} 
\frac{1-0.8z^{-1}}{1-2z^{-1}}
$$
- $|z|>2$, ne-stabilní, kauzální
- $|z|<2$, stabilní, nekauzální

Oba jsou platné inverzní systémy, nejsou však použitelné.

> [!tip] -> Použijeme all-pass filtr!

> [!info] Převod na systém s minimální fází:

$$
H(z) = 
\frac{1}{0.5} 
\frac{1-2z^{-1}}{1-0.8z^{-1}}
\frac{z^{-1}-2}{1-2z^{-1}}
$$

$$
H(z) 
= 0.5 \frac{z^{-1}-2}{1-0.8z^{-1}}
= 0.5(-2) \frac{1-0.5z^{-1}}{1-0.8z^{-1}}
$$
### Řešení
Určíme inverzní systém:
$$
G(z) = -1 \frac{1-0.8z^{-1}}{1-0.5z^{-1}}
$$
1) $|z| > 0.5$, bereme
2) $|z| < 0.5$


## Příklad
$y[n] = 0.25y[n-2] + x[n]$

- $x[n] = \delta[n-1]$
- $y[-1] = y[-2] = 1$

### Postup
- $y[n] -> Y(z)$
- $y[n-1] -> z^{-1}Y(z) + y[-1]$
- $y[n-2] -> z^{-2}Y(z) + y[-1]*z^{-1}$
$$
Y(z) = 0.25\left(
    Y(z)z^{-2} + z^{-1} +1
\right) + z^{-1}
$$

$$
Y(z)-0.25Y(z)z^{-2} = 1.25z^{-1} + 0.25
$$

$$
Y(z) = \frac{1.25z^{-1} + 0.25}{1-0.25z^{-2}}
$$

- $|z| > 0.5$

Rozklad na parciální zlomky:
- vzorec,
- křížové pravidlo,
- matlab: `residuez()`.
  
```matlab
b = [0.25, 1.25];
a = [1, 0, -0.25];
[z, p, k] = residuez(b, a)
```

- $A = 11/8$
- $B = -9/8$
- $\alpha = +-1/2$

$$
y[n] = A\alpha_1^n + B\alpha_2^n
$$
### Řešení
$$
y[n] = 
\frac{11}{8}(\frac{1}{2})^n\mu[n] 
- \frac{9}{8}(-\frac{1}{2})^n\mu[n]
$$