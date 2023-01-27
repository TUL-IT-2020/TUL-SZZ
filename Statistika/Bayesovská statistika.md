# Bayesovská statistika
**Tradiční statistika** = odhadujeme sice neznámý, ale deterministický parametr X
**Bayesovská statistika** = uvažujeme $\theta$ jako náhodnou veličinu, jejíž konkrétní realizaci musíme odhadnout

Parametr $\theta$ je náhodná veličina -> má [[Hustota pravděpodobnosti|hustotu pravděpodobnosti]] = prior pdf (apriorní hustota)
• Tu v klasických odhadech nelze využít
• Odvozujeme aposteriorní pdf na základě Bayesovy věty
• Odhad parametru odvozujeme z jeho aposteriorního rozdělení
• V případě, že neexistuje MVUE (nestranný odhad s minimální variancí), může Bayesovský odhad být odhadem, jehož MSE (mean square error) je menší než u ostatních odhadů.

## Bayesova věta
Bayesův vzorec:
$$
p(x,\theta) = p(x,\theta)p(\theta) = p(\theta, x)p(x)
$$

Bayesova věta:
$$
p(\theta|x) = \frac
	{p(x,\theta)p(\theta)}
	{p(x)}
= \frac
	{p(x,\theta)p(\theta)}
	{\int p(x, \theta)p(\theta) d\theta}
$$
Hustotu $p(\theta)$ je apriorní hustota pravděpodobnosti $\theta$, zatímco $p(\theta, x)$ je aposteriorní hustota. 
Dále platí: 
$p(y,x) = p(y) ⇔ y,x$ 𝑗𝑠𝑜𝑢 𝑛𝑒𝑧á𝑣𝑖𝑠𝑙é.

## Bayesovský odhad s nejmenší kvadratickou chybou
Odhad minimalizující střední kvadratickou chybu (MSE)
$$
mse(\hat\theta) = E \left[(\hat\theta - \theta)^2 \right] 
= \int (\hat\theta - \theta)^2 p(x|\theta)dx
$$
Bayesovský MSE odhad
$$
Bmse(\hat\theta) = E \left[(\hat\theta - \theta)^2 \right] 
= \int \int (\hat\theta - \theta)^2 p(x,\theta)dxd\theta
$$
Můžeme upravit na:
$$
Bmse(\hat\theta) = E \left[(\hat\theta - \theta)^2 \right] 
= \int \left[ \int (\hat\theta - \theta)^2 p(\theta|x)d\theta \right] p(x) dx
$$
## Bayesovské odhady
1. Hledáme odhad, který minimalizuje $Bmse(\hat\theta)$
2. Derivujeme $\int (\hat\theta - \theta)^2 p(\theta|x)d\theta$ podle $\theta$ a položíme rovno nule.
3. Výsledný odhad je
$$
\hat\theta_{BMSE} = E[\theta|x] = \int \theta p(\theta|x)d\theta
$$
což je rovno střední hodnotě aposteriorního rozložení.

### Příklad
Uvažujme model $𝑥[𝑛] = 𝐴 + 𝑤[𝑛]$, kde $w[n]\sim N(0,1)$ a $A$ je neznámý parametr, který chceme uvažovat. Pro odhad chceme využít expertní znalost, že $A\sim N(\mu A, 1)$. Jak bude vypadat BMSE odhad parametru $A$?

Odhad $\hat A$ tradiční statistikou by byl $\hat A = \frac{1}{N} \sum^N_{i=1} x_i$, zatímco odhad pouze z apriorní hustoty by byl $\hat A = E[A] = \mu_A$. Výsledný Bayesovský odhad je (odvozeno při přednášce)
$$
\hat A_{BMSE} = \frac{N}{N+1}\hat A 
+ \frac{1}{N+1}\mu_A
$$
Co to znamená?

## Metody Bayesovských odhadů
### Minimum Mean Square Error
$$
Bmse(\hat\theta) = E \left[(\hat\theta - \theta)^2 \right] 
= \int \left[ \int (\hat\theta - \theta)^2 p(\theta|x)d\theta \right] p(x) dx
$$
$$
\hat\theta_{MSE} = E[\theta|x] = \int \theta p(\theta|x)d\theta
$$
### Maximum A posteriori Estimators
$$
\hat\theta_{MAP} = arg\;max \; p(\theta|x)
$$
$$
p(\theta|x) = \frac 
	{p(x|\theta)p(\theta)}
	{p(x)}
$$
$$
\hat\theta_{MAP} = arg\; max_\theta \; p(x|\theta)p(\theta)
$$


### Příklad
Odhad parametru $\theta$ exponenciálního rozdělení, pokud předpokládáme apriorní hustotu jako $p(\theta) = \lambda e ^{-\lambda\theta}$, pro $\theta > 0$ a $p(\theta) = 0$ jinak.