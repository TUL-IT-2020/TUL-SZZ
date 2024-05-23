# Signály

## Základní signály
### $\delta[n]$ - jednotkový impulz
![[Wiki-Dirac_distribution.png]]

### $u[n]$ - jednotkový skok
![[Wiki-jednotkovy_skok.png]]
### Komplexní exponenciála
$$
x[n] = e^{j\omega_0n} 
$$
- $ω_0 \in R$ 
Eulerova notace: 
$$
e^{j\omega_0n} = cos[\omega_0n] + j sin[\omega_0n]
$$
## Perioda
$x[x] = sin(\pi/8 * n)$
$2\pi = \pi/8 * N$
$N = 16$

Změna vzorkování:
$x[n] = sin(1/8n)$
$2\pi = 1/8*N$
$N = 16\pi$

V diskrétních čísel musí být perioda celočíselná a proto tento signál není periodická. 
## Převzorkování signálů
$m = 2n - 3$
Inverzní funkce:
$n = \frac{m+3}{2}$

## Příklady
![[Signály příklady|Signály příklady]]

## Reálné signály
Vlastnosti reálných signálů:
- mají konečnou délku -> málo dat,
- nestacionarita -> frekvenční složka času se mění v čase,
- šum