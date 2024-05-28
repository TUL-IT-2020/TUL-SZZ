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
![[Z-transformace příklad inverzních filtrů]]


# Numerické řešení
## Příklad
- $ax^2 + bx + c = 0$
- $a(x-x_1)(x-x_2)$
### Postup
$$
H(z) = \frac{1}{1-az^{-1}}
$$
- $|z| > 1/2$
- $k[n] = 1/2^n u[n]$

$$
\frac{1}{1-az^{-1}} = 1+1/2z^{-1}+1/4z^{-2}
$$

$$
\frac{-1 +- 1/2z^{-1}}
{1/2 z^{-1}}
$$

$$
\frac{- 1/2z^{-1} +- 1/4z^{-2}}
{0+1/4 z^{-2}}
$$

...

# Analytické řešení
## Příklad
$$
y[n] = 3/4 y[n-1] - 1/8 y[n-2] + x[n]
$$

Počáteční podmínky:
- $x[n] = \delta[n]$,
- $y[-1] = -1$, 
- $y[-2] = 1$

$Z_1$:
- $y[0] ->^{Z_1} Y(z)$
- $y[n-1] -> Y(z)z^{-1}+(-1)$
- $y[n-2] -> Y(z)z^{-2}-z^{-1}+1$

### Postup
$$
Y(z) = 
\frac{1}{3} (Y(z)z^{-1} - 1) 
- \frac{1}{8} (Y(z)z^{-2} -z^{-1} + 1) 
+ 1
$$

$$
Y(z) (1 - 3/4z^{-1} + 1/8z^{-2}) = 1/8z + 1/8z^{-1}
$$

$$
Y(z) = \frac{1/8z + 1/8z^{-1}}{1 - 3/4z^{-1} + 1/8z^{-2}}
$$

Zpět do časové oblasti:
```matlab
b = [1/8 1/8];
a = [1 -3/4 1/8];
[r,p,k] = residuez(b,a)
```

### Řešení
$y[n] = 3/4*1/2^n \mu[n] - 5/8*1/4^n \mu[n]$

```matlab
% analytické řešení
b = [1];
a = [1 -3/4 1/8];
ic = [-1 1];

N = 20;
n = 0:N;
x =  [1, zeros(1,N)];
% počáteční podmínky
flt_ic = filtic(b,a,ic);
[y, Zf] = filter(b,a,x,flt_ic);

figure;
stem(n,y);
hold on;

% analytické řešení
y2 = (3/4)*(1/2).^n - (5/8)*(1/4).^n;
stem(n,y2);

% porovnání:
sum((y-y2').^2)
```

## Příklad
$$
H(z) = \frac{
    4 - 7/4z^{-1} + 1/4z^{-2}
}{  
    1-3/4z^{-1} + 1/8z^{-2}
}
$$
- $|z| > 1/2$

- FIR/IIR?
- Kauzalní?
- Stabilní?

### Postup:
IIR, stabilní, kauzalní

Póly:
$$
H(z) = \frac{
    4 - 7/4z^{-1} + 1/4z^{-2}
}{  
    (1-1/2z^{-1})(1-1/4z^{-1})
}
$$

Nuly:
```matlab
% nuly
roots([4 -7/4 1/4])

% poloměr kružnice
abs(roots([4 -7/4 1/4])) 
```

- $\beta_1 = \beta_2 = 0,21+0,12$
- $|\beta_1| = 0.25$ 

$$
G(z) = \frac
{(1-1/2z^{-1})(-1/4z^{-1})}
{(1-\beta_1 z^{-1})(1-\beta_2 z^{-1})}
$$

1) $|z| > 1/4$, inverzní, kauzalní, stabilní
2) $|z| < 1/4$, neplatný, nekauzalní, nestabilní

Filtr s minnimální fází - všechny nuly jsou unvitř jednotkové kružnice

```matlab
zplane(b,a)
```


$$
h[n] = 2\delta[n] + 3*1/2^n\mu[n] - 1/4^n\mu[n]
$$

Frekvenční charakteristika:
- $z = e^{j\omega}$
$$
H(e^{j\omega}) = \frac
{4 - 7/4 e^{-j\omega} + 1/4 e^{-j2\omega}}
{1-3/4 e^{-j\omega} + 1/8 e^{-j2\omega}}
$$

```matlab
% frekvenční charakteristika
freqz(b,a,1000)
[h,w] = freqz(b,a,1000);
figure;
plot(w/pi, abs(h));
```

Kontrola dosazením nulové frakvence:
$$
H(e^{j0}) = \frac
{4 - 7/4 + 1/4}
{1-3/4 + 1/8}
= \frac{20}{3}
= 6,6...
$$

### Řešení:
$$
Y(e^{j\omega})(1-3/4 e^{-j\omega} + 1/8 e^{-j2\omega})
= 
X(e^{j\omega})(4 - 7/4 e^{-j\omega} + 1/4 e^{-j2\omega})
$$

$$
y[n] - 3/4 y[n-1] + 1/8 y[n-2] = 4x[n] - 7/4 x[n-1] + 1/4 x[n-2]
$$

## Příklad

$$
H(z) = \frac
{1 - 4z^{-1} + 5z^{-2}}
{1 - 1z^{-1} + 1/2z^{-2}}
$$
- $|z| > 0,7071$

Má inverzní systém?

### Postup
Zjistíme nuly.
```matlab
% nuly
roots([1 -4 5])
```
- $\beta_{1,2} = 2+-1j$
- $|z| > \sqrt{5}$

Trik s all-pass filtrem:
$$
H(z) = \frac
{(1 - \beta_1 z^{-1})(1 - \beta_1 z^{-1})}
{1 - 1z^{-1} + 1/2z^{-2}}
* \frac
{z^{-1}-\beta_1}
{1 - \beta_1 z^{-1}}
* \frac
{z^{-1}-\beta_2}
{1 - \beta_2 z^{-1}}
$$

$$
H_{min}(z) = \frac
{(z^{-1}-\beta_1)(z^{-1}-\beta_2)}
{1 - 1z^{-1} + 1/2z^{-2}}
=
\frac
{z^{-2} - 2Re(\beta)z^{-1} + |\beta|^2}
{1 - 1z^{-1} + 1/2z^{-2}}
$$

$$
H_{min}(z) = \frac
{z^{-2} - 4z^{-1} + 5}
{1 - 1z^{-1} + 1/2z^{-2}}
$$
- $|z| > 0,7071$

```matlab
zplane([1 -4 5], [1 -1 1/2])
```
