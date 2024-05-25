# LTI (Linear Time Invariant) systémy
Jsou systémy s pěknými vlastnostmi:
- Lineární
- Časově nezávislé

Díky tomu na nich platí:
- Aditivita - Sčítání signálů
- Homogenita - Násobení konstantou

> [!warning] Důležité:
> Nejdůležitější charakteristikou LTI systému je jeho impulzní odezva, protože konvolucí vstupu s impulzní odezvou můžeme získat výstup LTI systému.

## Podrobněji

- lineární a časově nezávislé systémy
- u spojitých systémů jejich chování popisují diferenciální rovnice s konst. koeficienty
$$
a_n \frac{d^n y(t)}{dt^n} + a_{n-1} \frac{d^{n-1} y(t)}{dt^{n-1}} + ... + a_1 \frac{dy(t)}{dt} + a_0 y(t) = b_m \frac{d^m x(t)}{dt^m} + b_{m-1} \frac{d^{m-1} x(t)}{dt^{m-1}} + ... + b_1 \frac{dx(t)}{dt} + b_0 x(t)
$$
- u diskrétních (číslicových) systémů jejich chování popisují diferenční rovnice s konst. koeficienty

### Odvození diferenční rovnice

první derivaci u diskrétních systémů nahradíme rozdílem
$$
x'(n) = {x(n) - x(n-1)}
$$

druhou derivaci
$$
x''(n) = {x'(n) - x'(n-1)} = {x(n) - 2x(n-1) + x(n-2)}
$$
atd.

Dosazedním do diferenciální rovnice dostaneme diferenční rovnici
$$
A_0 y(n) + A_1 y(n-1) + ... + A_n y(n-N) = B_0 x(n) + B_1 x(n-1) + ... + B_m x(n-M)
$$

ta lze přepsat do podo
$$
y(n) = B'_0 x(n) + B'_1 x(n-1) + ... + B'_m x(n-M) - A'_1 y(n-1) - ... - A'_n y(n-N)
$$

je li $N=0$ a je systém nerekurzivní FIR(Finite Impulse Response) - systém s konečnou odezvou, v opačném případě je rekurzivní IIR(Infinite Impulse Response) - systém s nekonečnou impulstní. odezvou

### Klíčové vlastnosti LTI systémů
Chování libovolného LTI systému lze popsat pomocí odezvy na jednotkový impulz $h[n]$, tato operace se nazývá [[Konvoluce]].