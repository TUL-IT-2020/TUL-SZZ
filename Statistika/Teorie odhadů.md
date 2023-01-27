# Teorie odhadů
## Definice: 
𝑶𝒅𝒉𝒂𝒅𝒆𝒎 𝑛𝑒𝑧𝑛á𝑚éℎ𝑜 𝑝𝑎𝑟𝑎𝑚𝑒𝑡𝑟𝑢 $\theta$ 𝑛𝑎𝑧𝑣𝑒𝑚𝑒 𝑙𝑖𝑏𝑜𝑣𝑜𝑙𝑛𝑜𝑢 𝑓𝑢𝑛𝑘𝑐𝑖 $\theta = 𝑔(𝑋_1, 𝑋_2, … , 𝑋_𝑛)$ , která nezávisí na skutečné hodnotě $\theta$. 

### Poznámka: 
Odhad parametru může záviset i na jiných parametrech, pokud jsou známé. 

$\hat \theta$ ... odhad
$\theta$ ... veličina

### Příklady odhadů:
Uvažujme náhodný výběr $𝑋_1, 𝑋_2, … , 𝑋_𝑛$, který vznikl měřením zašuměného stejnosměrného proudu. Matematicky lze model popsat jako $𝑋_𝑖 = 𝐴 + 𝑤_𝑖$ , kde $A$ je konstantní a $w_i\sim N(0,1)$ , tzv. bílý šum. Úkolem je odhadnout hodnotu $A$.
- Varianta 1: $\hat A = \frac{1}{n} \sum^{n}_{i=1} X_i$
- Varianta 2: $\hat A = X_1$
Jaký odhad je lepší?

## Kvalita odhadu
### Definice:
𝑂𝑑ℎ𝑎𝑑 𝑛𝑒𝑧𝑛á𝑚éℎ𝑜 𝑝𝑎𝑟𝑎𝑚𝑒𝑡𝑟𝑢 $\theta$ 𝑛𝑎𝑧𝑣𝑒𝑚𝑒 **𝒏𝒆𝒔𝒕𝒓𝒂𝒏𝒏ý**, 𝑗𝑒𝑠𝑡𝑙𝑖ž𝑒 𝑝𝑙𝑎𝑡í: $E[\hat \theta] = \theta$.
Poznámka: Pokud odhad není nestranný, tzn. $E[\hat \theta] = \theta + b(\theta)$ , pak $b(\theta)$ nazveme bias, neboli **vychýlení** odhadu.

### MVUE (= minimum variance unbiased estimator) 
Takto nazveme nestranný odhad s minimálním rozptylem.

Pro ten platí:
• Nemusí vždy existovat,
• Pokud existuje, může být obtížné ho najít,
• Rozptyl nestranného odhadu nemůže být menší než [[Rao-Cramérova dolní mez|Cramérova-Raova dolní mez (CRLB)]]

## Vektorově
Odhadovaný parametr:
$$
\theta
= \begin{pmatrix}
\theta_1 \\\ 
... \\\ 
\theta_d 
\end{pmatrix}
$$
Např. $\theta = \begin{pmatrix} \mu \\\ \sigma^2 \end{pmatrix}$, tedy parametry Normálního rozdělení, nebo odhad kovarianční matice, lineární regrese. Už jsme viděli, že nestranný odhad $\sigma^2$ se liší v případech, kdy (ne)známe skutečnou hodnotu parametru $\mu$.
1. Známe $\mu$:
$$
\hat\sigma^2 = \frac{1}{N} \sum^N_{i=1} {(X_i - \mu)^2}
$$
2. Neznáme $\mu$ a nahradíme ho výběrovým průměrem:
$$
\hat\sigma^2 = \frac{1}{N-1} \sum^N_{i=1} {(X_i - \bar X_N)^2}
$$
