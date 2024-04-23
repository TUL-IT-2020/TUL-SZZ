## Z-Transformace

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