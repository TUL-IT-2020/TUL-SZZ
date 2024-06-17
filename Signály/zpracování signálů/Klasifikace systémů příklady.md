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
- není kauzální (`[n+1]`)
- stabilní 
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
- není kauzální
- není aditivní (+1)
- není homogenní
## Příklad
Rozhodněte a zdůvodněte: 
1. Je systém $𝑦[𝑛] = 𝑥[𝑛] + 𝑥[𝑛 −1]+𝑥[𝑛 −2]$ invariantní vůči posunu? 
2. Je systém $𝑦[𝑛] = log(𝑥[𝑛])$ homogenní? 
3. Je systém $𝑦[𝑛] = 𝑥[|𝑛|]$ kauzální?

### Postup

2.
$\cdot$
$c \cdot 𝑦[𝑛] ?= log(c\cdot 𝑥[𝑛])$

[[log.gif]]

$c \cdot 𝑦[𝑛] != log(c) + log(𝑥[𝑛])$

3.
n = -5
$y[-5] = x[5]$
Výstup závisí na budoucím vzorku.
### Řešení
1. Ano
2. Ne
3. Ne

## Který z následujících systémů je homogenní:
Rozhodněte a zdůvodněte, který z následujících systémů je homogenní:
1) $y[n] = log(x[n])$
2) 
$$
y[n] = 6x[n+2] + 4x[n+1] + 2x[n+1]
$$
3) 
$$
y[n] = 6x[n] + \frac{x[n+1]x[n-1]}{x[n]}
$$
## Příklad nestacionárního signálu:
$y[n] = nx[n]$

$nx[n] != (n-n_0)x[n-n_0]$
- nestacionárního

## Příklad
$y[n] = log(x[n])$

### Řešení
Je kauzální. 
V současném čase výstup závisí pouze na aktuálním vstupu. 