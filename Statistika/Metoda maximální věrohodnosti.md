# Metoda maximální věrohodnosti
PDF jako funkci neznámého parametru nazýváme [[Věrohodnost-Rozptyl_odhadu|věrohodnostní funkce (likelihood function)]]:
$$
p(\theta|x) = \prod^N_{i=1} {p(\theta|x_i)}
$$
## Princip
Princip maximálně věrohodného odhadu (Maximum Likelihood Estimation – MLE):
Maximalizovat věrohodnost = odhadnout neznámý parametr tak, aby „co nejlépe“ odpovídal modelu dat.
1. Často se opět využívá místo věrohodnostní funkce její logaritmus, tzv. log-likelihood function (označme symbolem ℒ).
2. Derivace ℒ → používá se pro nalezení maxima, tedy:
$$
\left[ 
	\frac{\partial\ln p(\theta|x)}{\partial\theta} 
\right] = 0
$$

## Vlastnosti
Asymptotické rozdělení MLE odhadu:
$$
\hat\theta_{MLE} \sim N(\theta, J^{-1}(\theta))
$$
- $J^{-1}(\theta)$ je inverze [[Rao-Cramérova dolní mez#Fisherova informace (FI)|Fisherovy informační matice]].

Důsledky:
1. MLE odhady jsou asymptoticky nestranné.
2. MLE odhady jsou asymptoticky eficientní! Dosahují [[Rao-Cramérova dolní mez|CRLB]].
3. Přesnost MLE odhadů se dá (někdy) analyticky odvodit.

## Příklady:
1. Jak vypadá MLE odhad střední hodnoty exponenciálního rozdělení?
2. Jak vypadá MLE odhad parametru $\mu$ pro rozdělení, které má hustotu pravděpodobnosti:
$$
f_X(x) = \frac{\beta}{2\alpha Γ(\frac{1}{\beta})} e^{-\left(\frac{ |x-\mu|}{\alpha}\right)^\beta}
$$
- $a = 1$

## MLE – numerické řešení

Nelze nalézt analyticky taková $\theta$, že platí:
$$ 
\frac{\partial\ln p(\theta|x)}{\partial\theta} = 0
$$
Proto označme:
$$
g(\theta) = \frac{\partial\ln p(\theta|x)}{\partial\theta}
$$
A využijme rozvoj funkce $g(\theta)$ v okolí bodu $\theta_0$:
$$
g(\theta) \approx g(\theta_0) 
+ \frac{\partial g(\theta)}{\partial\theta}|_{\theta=\theta_0}(\theta-\theta_0)
$$
A z toho odvodíme vztah:
$$
\theta_1 = \theta_0 
- \frac
	{g(\theta_0) }
	{\frac
		{\partial g(\theta)}{\partial\theta}|_{\theta=\theta_0}
	}
$$
A následně rekurentní vztah:
$$
\theta_{k+1} = \theta_k 
- \frac
	{g(\theta_0) }
	{\frac
		{\partial g(\theta)}{\partial\theta}|_{\theta=\theta_0}
	}
$$
Tato iterativní procedura se nazývá Newton-Raphsonův algoritmus.

### Poznámky: 
- Hrozí problémy s konvergencí (obzvláště pokud druhá derivace log-likelihood je malá) 
- Velmi závisí na inicializaci (při špatné inicializaci hrozí konvergence k lokálním maximům, ale dokonce i minimům).