# Rao-Cramérova dolní mez (CRLB)
## Skalárně
Předpokládejme, že hustota pravděpodobnosti $𝑝(\theta|𝒙)$ splňuje podmínku regularity. Potom rozptyl libovolného nestranného odhadu splňuje:
$$
var(\hat \theta) \geq \frac{1}{- E \left[ \frac{\partial^2\ln p(\theta|x)}{\partial\theta^2} \right]}
$$
kde derivaci vyčíslíme ve skutečné hodnotě parametru $\theta$.
Tuto mez nazýváme Rao-Cramérova dolní mez (Cramér-Rao Lower Bound = CRLB). 
Nestranný odhad, který dosahuje CRLB je **nejlepší nestranný odhad** (někdy také eficientní). 

Další vlastnosti CRLB:
- Pokud lze vyjádřit $\frac{\partial}{\partial\theta} \ln p(\theta|x) = I(\theta)(g(x) - \theta)$, kde $I(\theta)$ a $g(x)$ jsou libovolné funkce (ovšem závislé jenom na argumentu, který je zapsaný, popř. na hyperparametrech), pak $\hat \theta = g(x)$ je [[Teorie odhadů#Kvalita odhadu|nestranný odhad]] dosahující CRLB.
- Máme-li [[Statistická závislost a nezávislost#I.I.D. (independent identically distributed)|i.i.d. model]] dat a tedy $p(\theta|x) = \prod^N_{i=1} {p(\theta|x_i)}$, pak Fisherova informace celého pozorování $𝑥_1 … 𝑥_𝑁$ je rovna $N$-násobku Fisherovy informace jednoho (kteréhokoliv) pozorování. CRLB má potom nutně tvar násobku $\frac{1}{N}$.

### Fisherova informace (FI)
$$
J(\theta) = - E \left[ \frac{\partial^2\ln p(\theta|x)}{\partial\theta^2} \right]
$$
Pro FI platí:
$$
J(\theta) = - E \left[ \frac{\partial^2\ln p(\theta|x)}{\partial\theta^2} \right] = E \left[ \left( \frac{\partial}{\partial\theta} \ln p(\theta|x) \right)^2 \right]
$$

## Vektorově
Fisherova informace je pro případ odhadu vektoru parametrů reprezentovaná **Fisherovou Informační Maticí** (FIM) $F(\theta)$.
Pro $F(\theta)$ platí:
$$
F(\theta)_{i,j} = 
E \left[ 
	\left(
		\frac{\partial \ln f(\theta|x)}{\partial\theta_i}
	\right)
	\left(
		\frac{\partial \ln f(\theta|x)}{\partial\theta_j}
	\right)
\right] = 
- E \left[ 
	\frac{\partial^2}{\partial\theta_i\partial\theta_j}
	\ln f(\theta|x) 
\right]
$$
Nechť $\hat\theta$ je nestranný odhad parametru $\theta$ tj. $E[\hat\theta] = \theta$. Platí, že:
$$
cov(\hat\theta) \geq F^{-1}(\theta)
$$
což znamená, že matice  $cov(\hat\theta) - F^{-1}(\theta)$ je pozitivně semidefinitní.

### Příklad:
Nechť $\alpha$ je vektor stejných rozměrů jako $\theta$. Uvažujme skalární odhad $\hat\alpha = \alpha^T\hat\theta$ , což je nestranný odhad $\alpha^T\theta$. Pak platí:
$$
var(\hat\alpha) = cov(\alpha^T\hat\theta) = \alpha^T cov(\hat\theta)\alpha \geq \alpha^T F^{-1}(\theta)\alpha
$$
Když například $alpha = (1,0,...)^T$, pak $\hat\alpha = \alpha^T\hat\theta = \hat\theta_1$, a CRLB říká, že $var(\hat\theta_1) \geq F^{-1}(\theta)_{11}$.

### Pro gaussovská pozorování:
Nechť $x\sim N(\mu(\theta), C(\theta))$, kde $\theta$ jsou parametry modelu a tedy $\mu(\theta)$ a $C(\theta)$ popisují (obecně nelineární) závislost střední hodnoty a [[Kovariance, kovarianční matice#Kovarianční maticí nazýváme matici|kovarianční matice]] pozorování na těchto parametrech. 
Pro FIM $F(\theta)$ platí:
$$
F(\theta)_{i,j} = \left[ 
	\frac{\partial \mu(\theta)}{\partial\theta_i} 
\right]^T
C^{-1}(\theta)\frac{\partial \mu(\theta)}{\partial\theta_j}
+ \frac{1}{2} tr \left[
	C^{-1}(\theta)\frac{\partial C(\theta)}{\partial\theta_i}
	C^{-1}(\theta)\frac{\partial C(\theta)}{\partial\theta_j}
\right]
$$