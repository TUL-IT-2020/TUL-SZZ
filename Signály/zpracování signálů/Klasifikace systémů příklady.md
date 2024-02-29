#příklad  
# Klasifikace systémů
## Příklad
### Systém
$$y[n] = 4*x[n+1] + 2x[n] +1$$
### Řešení
- nekauzální
- stabilní (`[n+1]`)
- není aditivní (+1)
- není homogenní

$4*x[n+1] + 2x[n] +1 ?= c(4*x[n+1] + 2x[n] +1)$

$4*x[n+1] + 2x[n] +1 ?= 4*c*x[n+1] + 2*c*x[n]$

## Příklad nekauzálního signálu:
$y[n] = nx[n]$

$nx[n] != (n-n_0)x[n-n_0]$
- nekauzální