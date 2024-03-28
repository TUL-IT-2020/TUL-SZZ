# DFT

## Příklad:
$$x[n] = \delta[n-0] - 2\delta[n-1] + 4\delta[n-3]$$
$X[k] = ?$

- $N = 4$

### Postup:
- $k = 0$
- $\omega_0 = \frac{2\pi*0*0}{4}$
$$
x[0] = 1* e^{-j\frac{2\pi*0*0}{4}} 
+ 2 * e^{-j\frac{2\pi*0*1}{4}} 
+ 4 * e^{-j\frac{2\pi*0*3}{4}} 
+ = 1 + 2 + 4 = 7
$$

- $k = 1$
- $\omega_1 = \frac{2\pi*1*1}{4} = \pi/2$
$$
x[1] = 1* e^{-j\frac{2\pi*1*0}{4}} 
+ 2 * e^{-j\frac{2\pi*1*1}{4}} 
+ 4 * e^{-j\frac{2\pi*1*3}{4}} 
+ = 1 - 2j +4j = 1+2j
$$

$e^{-j\pi/2} = -j$
$e^{-j\pi*3/4} = +j$

- $k = 1$
- $\omega_1 = \frac{2\pi*1*1}{4} = \pi/2$
...