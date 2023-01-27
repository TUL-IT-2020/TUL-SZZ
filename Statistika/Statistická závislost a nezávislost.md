# Statistická závislost a nezávislost
## Definice:
Řekneme, že náhodné veličiny $X$ a $Y$ jsou statisticky nezávislé, jestliže platí $p(x,y) = p(x) p(y)$. Hustoty $𝑝(𝑥)$, $𝑝(𝑦)$ nazýváme **marginální** hustoty pravděpodobnosti. Pro marginální hustoty platí:
$$
p(x) = \int^\infty_{-\infty} p(x,y) \; dy
$$
- $p(x,y)$ ... nastane $x$ a zároveň $y$

### I.I.D. (independent identically distributed)
Nezávislé veličiny, které mají stejnou hustotu pravděpodobnosti (=stejné rozdělení / distribuční funkci) nazveme nezávislé stejně rozdělené a značíme i.i.d. (independent identically distributed).

## Příklad:
1. Uvažujme hod kostkou a označme si 2 jevy: 
	- $A$ - padne sudé číslo 
	- $B$ - padne číslo nepřevyšující 2. 
	- Jsou jevy A a B nezávislé? 
2. Upravme si drobně zadání, a uvažujme jev: 
	- $A$ - padne sudé číslo 
	- $B$ - padne číslo nepřevyšující 3. 
	- Jsou jevy A a B i nyní nezávislé?

### Odpovědi:
1. Jsou nezávislé
2. Jsou závislé