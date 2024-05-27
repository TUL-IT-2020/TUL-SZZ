# Konvoluce
$$
x[x] = \delta[n+1]*x[-1]
$$
## Příklad
$x[n] = 2\delta[n+2] + \delta[n+1] + \delta[n-1] + 3\delta[n-2]$
$h[n] = \delta[n-1] + \delta[n-2] + \delta[n-3]$
### Postup:
Tedy:
- signál `[2,1,0,1,3]`
- impulzní odezva: `[1,1,1]`

| $n$               | -2  | -1  | 0   | 1   | 2   | 3   | 4   | 5   |
| ----------------- | --- | --- | --- | --- | --- | --- | --- | --- |
| $h[n]$            |     |     |     | 1   | 1   | 1   |     |     |
| $T(2\delta[n+2])$ |     | 2   | 2   | 2   |     |     |     |     |
| $T(\delta[n+1])$  |     |     | 1   | 1   | 1   |     |     |     |
| $T(\delta[n-1])$  |     |     |     | 1   | 1   | 1   |     |     |
| $T(3\delta[n-2])$ |     |     |     |     |     | 3   | 3   | 3   |
| $T(x)$            | 0   | 2   | 3   | 3   | 2   | 4   | 4   | 3   |

## Příklad
Spočítejte:
$$
𝑦[𝑛] = ℎ[𝑛]④𝑥[𝑛] 
$$
- pro $𝑛 = (0..3)$

je-li dáno: 
- $ℎ[𝑛] = (𝑛 +1)(𝑢[𝑛]−𝑢[𝑛−4])$ 
- $x[𝑛] = 2𝛿[𝑛]−3𝛿[𝑛−2]+𝛿[𝑛−3]$ 

Zapište výsledek pomocí posunutých pulsů $𝛿[𝑛]$

### Postup:
$x=(2, 0, -3, 1)$
$h = (1,2,3,4)$
$L = 4+4-1 = 7$

| n     | 0   | 1   | 2   | 3   | 4   | 5   | 6   |
| ----- | --- | --- | --- | --- | --- | --- | --- |
| h     | 1   | 2   | 3   | 4   |     |     |     |
| $x.T$ |     |     |     |     |     |     |     |
| 2     | 2   | 4   | 6   | 8   |     |     |     |
| 0     |     | 0   | 0   | 0   | 0   |     |     |
| -3    |     |     | -3  | -6  | -9  | -12 |     |
| 1     |     |     |     | 1   | 2   | 3   | 4   |
| sum() | 2   | 4   | 3   | 3   | -7  | -9  | 4   |

Kruhová konvoluce:

| $y[0:3]$ | 2   | 4   | 3   | 3   |
| -------- | --- | --- | --- | --- |
| $y[3:6]$ | -7  | -9  | 4   |     |
| $sum()$  | -5  | -5  | 7   | 3   |
### Řešení
Výsledek kruhové konvoluce je: $y = (-5,-5,7,3)$
Tedy: $y[n] = -5\delta[n] -5\delta[n-1] +7\delta[n-2] +3\delta[n-3]$

## Příklad
Uvažujeme diskrétní sekvencí $x[n]$, jejíž nenulová hodnota je $x[−6] = 3$ a poslední nenulová hodnota $x[24] = −4$ (tedy sekvence má nenulové vzorky pouze pro $−6 ≤ n ≤ 24$).

Uvažujeme sekvenci vzniklou konvolucí:
$$
y[n] = x[n] ∗ x[n].
$$

1. Jaký je index prvního nenulového vzorku $y[n]$ a jaká jej jeho hodnota?
2. Jaký je index posledního nenulového vzorku $y[n]$ a jaká je jeho hodnota?
### Postup
$x[−6] = 3$ 
$x[24] = −4$

Délka konvoluce: $l_1 + l_2 -1$
$l_1 = 6+1+24 = 31$

|              | první vzorek | ... |     | ... |     | ... | poslední vzorek |
| ------------ | ------------ | --- | --- | --- | --- | --- | --------------- |
| $n$          | -12          |     | -6  |     | 24  |     | 48              |
| h            |              |     | 3   | ... | -4  |     |                 |
| $x.T$        |              |     |     |     |     |     |                 |
| $x[−6] = 3$  | 9            |     |     |     |     |     | 0               |
| ....         | 0            |     |     |     |     |     | 0               |
| $x[24] = −4$ | 0            |     |     |     |     |     | 16              |
| sum()        | 9            |     |     | ... |     |     | 16              |
### Řešení
- $L = 61$
- $y[-12] = 9$
- $y[48] = 16$
