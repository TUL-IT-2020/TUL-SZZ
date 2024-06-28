#příklad 
# Signály
## Příklad
$x[x] = sin(\pi/8 * n)$
### Postup
$2\pi = \pi/8 * N$
$N = 16$

### Řešení
Signál je periodický.

## Změna vzorkování:
$x[n] = sin(1/8n)$
### Postup
$2\pi = 1/8*N$
$N = 16\pi$

### Řešení
V diskrétních čísel musí být perioda celočíselná a proto tento signál není periodická. 

## Příklad
Určete, zda jsou signály dané dále periodické. Jsou-li, určete délku jejich základní periody:
1. $x[n] = sin(0.125\pi n)$
2. $x[n] = sin(0.125n)$

### Postup
$2\pi = 0.125\pi n = 1/8 \pi n$
$2*8 = n$
$n = 16$
- celé číslo, signál je periodický.

$2\pi = 0.125 n = 1/8 n$
$16\pi = n$
- není celé číslo, signál nebude periodický.

## Příklad inverzní funkce:
$m = 2n - 3$
$n = \frac{m+3}{2}$

## Jak bude vypadat signál?
$x[n] = (6-n)(u[n] - u[n-6])$
### Postup
- $(6-n)$ - klesající přímka
- $(u[n] - u[n-6])$ - výběr vzorků (0-5)

## Jak bude vypadat signál?
$x[n] = sin[\pi/4 n]$
- $n = 0...7$
- jinde: $x[n] = 0$

Zakreslete v časové oblasti:
1) průběh: $x[n]$
2) průběh: $y[n] = x[-2n+3]$

## Fáze na počet vzorků:
$$
cos(\pi/10n + \pi/2) = cos(\pi/10(n+5))
$$
Násobení jedničkou:
- $pi/2 * 1 = \pi /2 * 1/5 *5=(\pi /2 * 1/5)*5 = \pi/10*5$

$$
cos(\pi/2n + \pi/2) = cos(\pi/2(n+1))
$$

