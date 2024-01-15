#příklad
# Polynomy
## Příklad
$$
f(x) = 2x^6 + 5x^4 + 5x^3+x^2+ 3x + 4
$$
$$
g(x) = 6x^6 + 3x^5 +x^4+3x^2+ 3x + 1
$$
$$
q(x) = 5x^3+2x + 6
$$
- $\in Z_7[x]$

1. Rozhodněte zda: $f(x)\equiv g(x)(mod \; q(x))$
2. Určete $r(x)$, tak aby platilo: $r(x)=(g(x)mod\;q(x))$

### Postup
dělení polynomů: g(x)/q(x)
...
$g(x) = q(x)(4x^3+2x^2) + (5x^2+3x+1)$

dělení polynomů: f(x)/q(x)
...
$f(x)/q(x) = q(x)(6x^3+5) + (x^2+2)$
### Řešení
$f(x)\neq(x)(mod \; q(x))$
$r(x) = (g(x)mod\;q(x)) = (5x^2+3x+1)$

## Příklad
$f(x), g(x) \in Z_5[x]$
$$
f(x) = 3x^6 + x^5 + 2x^4 + x^2 + 4x + 2
$$
$$
g(x) = 4x^5 + 3x^3 + 3x^2 + 4x + 3
$$
Určete NSD(f,g), NSN(f,g), pomocí rozkladu na ireducibilní polynomy.
Určete všechny monické polynomy f(x) stupně 3, nebo 5.
Kolik je všech dělitelů a kolik monických?

### Postup
Najdeme kořeny polynomu.
- Dosazujeme 0,1,2,3,4, některé mohou být více násobné.

Vypočítáme hodnoty v bodě pro jednotlivá čísla:
- Když nám vyjde $f(x)=0$, narazili jsme na kořen.

| x | 0 | 1 | 2 | 3 | 4 |
| ---- | ---- | ---- | ---- | ---- | ---- |
| $f(x)$ | 2 | 3 | 0 | 0 | 3 |
| monický polynom |  |  | $(x+3)$ | $(x+2)$ |  |
Sestavíme tabulku:
- Přepíšeme do tabulky koeficienty polynomu.
- První sloupeček odpovídá hodnotě $x$.
- Poslední hodnotě $f(x)$.
- $mod(5)$!

| 3 | 3 | 1 | 2 | 0 | 1 | 4 | 2 |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
|  | / | 4 | 0 | 1 | 3 | 2 | 3 |
| 3 | 3 | 0 | 2 | 1 | 4 | 1 | 0 |
|  | / | 4 | 2 | 2 | 4 | 4 |  |
| 2 | 3 | 4 | 4 | 3 | 3 | 0 |  |
|  | / | 1 | 0 | 3 | 2 |  |  |
|  | 3 | 0 | 4 | 1 | 0 |  |  |
$f(x) = (x+3)(x+2)^2*(3x^3+4x+1)$
$f(x) = 3(x+3)(x+2)^2*(x^3+3x+2)$

Najdeme kořeny polynomu.
- Dosazujeme 0,1,2,3,4, některé mohou být více násobné.

| x | 0 | 1 | 2 | 3 | 4 |
| ---- | ---- | ---- | ---- | ---- | ---- |
| $g(x)$ | 3 | 2 | 0 | 0 | 0 |
| monický polynom |  |  | $(x+3)$ | $(x+2)$ | $(x+1)$ |

| 3   | 4   | 0   | 3   | 3   | 4   | 3   |
| --- | --- | --- | --- | --- | --- | --- |
|     | /   | 2    | 1    | 2    | 0    | 2    |
| 4   | 4    | 2    | 4    | 0    | 4    | 0    |
|     | /   | 1    | 2    | 4    | 1    |     |
| 2   | 4    | 3    | 1    | 4    | 0    |     |
|     | /   | 3    | 2    | 1    |     |     |
|     | 4    | 1    | 3    | 0    |     |     |

$g(x) = (x+3)(x+2)(x+1)(4x^2 + x +3)$
$g(x) = 4(x+3)(x+2)(x+1)(x^2 + 4x + 2)$


### Řešení
$NSD(f,g) = (x+3)(x+2) = x^2+5x+6 = x^2+1$
$NSN(f,g) = (x+3)(x+2)(x+2)(x+1)(x^3+3x+2)(x^2 + 4x + 2)$

Moničtí dělitelé f(x) stupně 3 nebo 5:
- Stupně 3:
$(x^3+3x+2)$
$(x+3)(x+2)^2$

- Stupně 5:
$(x^3+3x+2)(x+2)^2$
$(x^3+3x+2)(x+2)(x+3)$


Kolik je všech monických dělitelů f(x): $(1+1)(2+1)(1+1)=12$

Kolik je všech dělitelů f(x): $4*12$
- 4 - podle tělesa

## Příklad
$f(x), g(x) \in Z_5[x]$
$$
f(x) = 3x^7 + 4x^6 + x^5 + 3x^3 + 2x + 1
$$
$$
g(x) = 4x^5 + 3x^4 + 2x^3 + x^2
$$

Pomocí Euklidova algoritmu určete:
- NSD(f,g)
- NSN(f,g)

### Postup
Euklidův algoritmus:
$f(x) = g(x)*q_i + r_i$

| dělenec | dělitel | $q_i$ | $r_i$ |
| ---- | ---- | ---- | ---- |
| $3x^7 + 4x^6 + x^5 + 3x^3 + 2x + 1$ | $4x^5 + 3x^4 + 2x^3 + x^2$ | $2x^2+2x+4$ | $2x^4+3x^3+x^2+2x+1$ |
| $4x^5 + 3x^4 + 2x^3 + x^2$ | $2x^4+3x^3+x^2+2x+1$ | $2x+1$ | $2x^3+x^2+x+4$ |
| $2x^4+3x^3+x^2+2x+1$ | $2x^3+x^2+x+4$ | $x+1$ | $4x^2+2x+2$ |
| $2x^3+x^2+x+4$ | $4x^2+2x+2$ | $3x$ | $4$ |
4 ... poslední zbytek po dělení, polynom stupně 0 v monické formě "1".
### Řešení
$NSD(f,g) = 1$
$NSN(f,g) = f(x)g(x)$