#příklad  
# Klasifikace systémů
## Příklad
### Systém
$$
y[n] = 4\cdot x[n+1] + 2\cdot x[n] +1
$$
### Postup:
Homogenita:

$4\cdot cx[n+1] + 2cx[n] +1 ?= c(4\cdot x[n+1] + 2x[n] +1)$
$4\cdot cx[n+1] + 2cx[n] +1 ?= 4\cdot c\cdot x[n+1] + 2\cdot c\cdot x[n] + c$
### Řešení
- je kauzální
- stabilní (`[n+1]`)
- není aditivní (+1)
- není homogenní
## Příklad
$$
y[n] = 6x[n+2] + 4x[n+1]+2x[n] +1
$$
### Postup:
Aditivita:
$$
(6x[n+2] + 4x[n+1] + 2x[n] + 1)+k ?= 6(x[n+2])+k + 4(x[n+1])+k + 2(x[n])+k + 1
$$
Homogenita:
$$
k * (6x[n+2] + 4x[n+1] + 2x[n] + 1) ?= 6(kx[n+2]) + 4(kx[n+1]) + 2(kx[n]) + 1
$$
### Řešení
- je kauzální
- není aditivní (+1)
- není homogenní
## Příklad nekauzálního signálu:
$y[n] = nx[n]$

$nx[n] != (n-n_0)x[n-n_0]$
- nekauzální

## Příklad
$y[n] = log(x[n])$

### Řešení
Je kauzální. 
V současném čase výstup závisí pouze na aktuálním vstupu. 