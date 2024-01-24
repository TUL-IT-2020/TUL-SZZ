# Věrohodnost: Rozptyl odhadu
PDF jako funkci neznámého parametru nazýváme věrohodnostní funkce (likelihood function):
$$
p(\theta|x) = \prod^N_{i=1} {p(\theta|x_i)}
$$
Čím větší „sharpness“ křivky, tím lépe půjde odhadnout. Často se využívá místo věrohodnostní funkce její logaritmus, tzv. log-likelihood function (označmě symbolem ℒ). Derivace ℒ → používá se pro nalezení maxima. Pro uvažované hustoty pravděpodobnosti předpokládáme, že splňují podmínku „regularity“, tedy:
$$
E \left[ \frac{\partial\ln p(\theta|x)}{\partial\theta} \right] = 0
$$
... for all $\theta$

Druhá derivace ℒ → používá se pro popis tvaru křivky (konvexní / konkávní) Jaký průběh má pdf? Jaké znaménko má její derivace?