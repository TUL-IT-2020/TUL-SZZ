# Z-Transformace

## Příklad:
$$
h[n] = \delta[n] - \alpha\delta[n-1]
$$
### Postup
$$
H(z) = h[0] + h[1]z^{-1}
$$
$$
H(z) = 1 - \alpha z^{-1}
$$
- kde $|z| > 0$ 

## Příklad
$$
h[n] = (\delta[n] + \delta[n-1] + \delta[n-2]) 1/3
$$

### Postup
$$
H(z) = 1/3(1 + z^{-1} + z^{-2})
$$
$$
H(z) = \frac{1}{3} \frac{z^2 + z + 1}{z^2}
$$
### Řešení 
Nuly:
- $z^2 + z + 1 = 0$
- $z = ?$

Póly: 
- $z^2 = 0$, dvojnásobný

## Příklad
$$
H(z) = \frac
    {4 + 2/4z^{-1} + 1/4z^{-2}}
    {1-3/4z^{-1} + 1/8z^{-2}}
$$
- $|z| > 1/2$

### Postup
Je řád čitatele větší než jmenovatele?
- ne, musíme použít parciální zlomky

Uděláme podíl:
$$
\left(4 + 2/4z^{-1} + 1/4z^{-2}\right)/
\left(1-3/4z^{-1} + 1/8z^{-2}\right)
= 2 + zbytek
$$

$$
H(z) = 2 + \frac{A}{1-1/4z^{-1}} + \frac{B}{1-1/2z^{-1}}
$$
$$
H(z) = 2 + \frac{3}{1-1/2z^{-1}} + \frac{1}{1-1/4z^{-1}}
$$

$$
h[n] = 2\delta[n] + \left(3(1/2)^n - (1/4)^n\right)*u[n]
$$ 

## Příklad

$x[n] = 3\delta[n] + \delta[n-2] + \delta[n+2]$

### Postup
Z-transformace:
- $\delta[n] -> 1$
- $x[n-n_0] -> z^{-n_0}X(z)$

### Řešení
$X(z) = 3 + z^{-2} + z^{2}$
- $|z| > 0$
- $|z| < \infty$

## Příklad
$x[n] = 2^n \mu[n] + 3*(1/2)^n \mu[n]$

Z-transformace:
- $a^n\mu[n] -> \frac{1}{1-az^{-1}}$

### Řešení
$X(z) = \frac{1}{1-2z^{-1}} + \frac{3}{1-1/2z^{-1}}$
- $|z| > 2$, $|z| > 1/2$

Tedy:
- $|z| > 2$

## Příklad
$x[n] = 3^n \mu[-n]$

### Postup
$X[n] = --3^n \mu[-n-1] + 3^0\delta[n]$
- protože končí na -1, musíme první prvek přidat

$X[n] = \frac{1}{1-3z^{-1}} + 1$
- $|z| > 3$, all
### Řešení
$X(z) = \frac{-1+1-3z^{-1}}{1-3z^{-1}}= \frac{-3z^{-1}}{1-3z^{-1}}$
- $|z| < 3$

# inverzní Z-transformace
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