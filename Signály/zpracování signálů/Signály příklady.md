#příklad 
# Signály
## Příklad

$x[x] = sin(\pi/8 * n)$
$2\pi = \pi/8 * N$
$N = 16$

### Změna vzorkování:
$x[n] = sin(1/8n)$
$2\pi = 1/8*N$
$N = 16\pi$

V diskrétních čísel musí být perioda celočíselná a proto tento signál není periodická. 

## Příklad inverzní funkce:
$m = 2n - 3$
$n = \frac{m+3}{2}$

## Jak bude vypadat signál?
$x[n] = (6-n)(u[n] - u[n-6])$
### Postup
- $(6-n)$ - klesající přímka
- $(u[n] - u[n-6])$ - výběr vzorků (0-5)
## Fáze na počet vzorků:
$$
cos(\pi/10n + \pi/2) = cos(\pi/10(n+5))
$$

$$
cos(\pi/2n + \pi/2) = cos(\pi/2(n+1))
$$

