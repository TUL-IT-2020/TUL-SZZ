# Decibely

## Příklad na decibely
### Zadání
- $E_{ref} = 5$
- $+20 dB$
- $E_x = ?$
### Postup
$dB = 10 \cdot \log_{10}(\frac{E_x}{E_{ref}})$
$20 dB = 10 * log_{10}(x/5)$
### Řešení
$E_x = 100 * E_{ref}$

## Příklad
Užitečný signál:
$$
𝑥[𝑛] = 9𝛿[𝑛] + 3𝛿[𝑛 − 1] + 3𝛿[𝑛 − 2] + 𝛿[𝑛 − 3]
$$
je rušen šumem:
$$
𝑣[𝑛] = 0.5(𝑢[𝑛] − 𝑢[𝑛 − 4])
$$

Určete:
- Odstup signálu $𝑠[𝑛]$ od šumu $𝑣[𝑛]$ (Signal to Noise Ratio - SNR). 
- Energii signálu $𝑠_2[𝑛]$, který vznikne zeslabením $𝑠[𝑛]$ o 10 dB.
### Postup
$x = (9, 3, 3, 1)$
$v = 1/2*(1,1,1,1)$

$E_x = 81+9+9+1 = 100$ 
$E_v =  1/4*4 = 1$

$SNR = 10 * log_{10}(100/1)$
$SNR = 10 * log_{10}(100)$
$SNR = 10 * 2$
### Řešení
$SNR = 20$

$E_{s_2} = 10$