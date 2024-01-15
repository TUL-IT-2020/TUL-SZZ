#příklad 
# Největší společný dělitel 
NSD
Aplikace [[Euklidův algoritmus|Eukleidova algoritmu]].
Online kalkulačka: [hackmath NSD](https://www.hackmath.net/cz/kalkulacka/nejvetsi-spolecny-delitel).
## Příklad

$$
NSD(123123, 5678)=?
$$
### Postup
| dělenec | = | dělitel | * | $q_i$ | + | $r_i$ |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| 123123 | = | 5678 | * | 21 | + | 3885 |
| 5678 | = | 3885 | * | 1 | + | 1793 |
| 3885 | = | 1793 | * | 2 | + | 299 |
| 1793 | = | 299 | * | 5 | + | 298 |
| 299 | = | 298 | * | 1 | + | 1 |
### Řešení
Jsou nesoudělné, poslední zbytek po dělení vyšel 1.

## Příklad
$$
NSD(408, 453) =?
$$

### Postup
Opět pozor na to, že první sloupeček musí začínat vyšším ze dvou čísel! 

| dělenec | dělitel | zbytek |
| ---- | ---- | ---- |
| 453 | 408 | 45 |
| 408 | 45 | 3 |
| 45 | 3 | 3 |
| 3 | 3 = NSD(408, 453) | 0 |

### Řešení
Tedy hledaný $NSD(408, 453) = 3$.

## Příklad
$$
NSD(401, 340) =?
$$
### Postup

| dělenec | dělitel | zbytek |
| ---- | ---- | ---- |
| 401 | 340 | 61 |
| 340 | 61 | 35 |
| 61 | 35 | 26 |
| 35 | 26 | 9 |
| 26 | 9 | 8 |
| 9 | 8 | 1 |
| 8 | 1 = NSD(401, 340) | 0 |

### Řešení
Tedy hledaný $NSD(401, 340) = 1$. 
Pozn.: čísla 401, 340 jsou tedy nesoudělná, což Eukleidův algoritmus nijak neovlivní.
## Příklad
a = 106050 
b = 156450
NSD(a,b) = ?
### Postup

$$
NSD(a,b) = d*NSD(\frac{a}{d},\frac{b}{d})
$$

$a = 106050 = 50*2121$ 
$b = 156450 = 50*2129$

| dělenec | dělitel | $q_i$ | zbytek |
| ------- | ------- | ----- | ------ |
| 3129    | 2121    | 1     | 1008   |
| 2121    | 1008    | 2     | 105    |
| 1008    | 105     | 9     | 63     |
| 105        | 63        | 1      | 42     |
| 63        | 42        | 1      | 21     |
| 42        | 21        | 2      | 0       |
$NSD(a,b) = 50*21 = 1050$
### Řešení
NSD(a,b) = 1050

## Příklad dvojkový NSD algoritmus
a = 112
b = 161

### Postup
$112 = 2*56 = 2*28 = 2*14 = 2*7$

$\frac{161-7}{2}=77$
$\frac{77-7}{2}=35$
$\frac{35-7}{2}=14$
$\frac{14-7}{2}=7$
$7/7 = 0$

### Řešení
$NSD(112,161) = 7$