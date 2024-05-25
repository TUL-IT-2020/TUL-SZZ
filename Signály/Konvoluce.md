# Konvoluce
Matematická funkce postihující interakcí signálu a systému popsaného impulsní odezvou.

## Předpis
> [!important]
$$
y[n] = x[n]*h[n] = \sum_{k=-\infty}^{\infty} x[k] h[n-k]
$$

> [!note] V Matlabu:
> `filter(b,a,x)`
> `conv(x,h)`
> - délka výsledného signálu $= x.l+h.l-1$

## Příklady
![[Konvoluce příklad]]