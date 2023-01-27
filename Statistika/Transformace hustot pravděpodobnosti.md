# Transformace hustot pravděpodobnosti
## Skalárně
Uvažujme [[Náhodná veličina|náhodnou veličinu]] $X$, a z ní vytvořme náhodnou veličinu $Y$ jako $Y = h(X)$.

Nechť $X$ je [[Hustota pravděpodobnosti#Absolutně spojité náhodné veličiny|spojitá náhodná veličina]], $ℎ ∶ 𝑅 → 𝑅$ ryze monotónní funkce na množině $X(\ohm)$ a $h^{-1}$ je diferencovatelná. Potom náhodná veličina $Y = h(X)$ má [[Hustota pravděpodobnosti|hustotu pravděpodobnosti]]:
$$
f_Y(y)=f_X \left( h^{-1} (y) \right) \left| \frac{dh^{-1}(y)}{dy} \right| 
$$
a navíc
$$
F_Y(y) = F_X \left(h{-1}(y) \right)
$$

### Důležité:
Pro [[Střední hodnota a rozptyl#Střední hodnota|střední hodnoty]] platí: $𝐸[𝑌] = 𝐸[ℎ(𝑋)]$

- Díky tomuto pravidlu můžeme používat operátor střední hodnoty aniž bychom konkrétně uváděli podle které hustoty pravděpodobnosti (distribuční funkce) se počítá.

### Příklady: 
1. $𝑌 = 𝑎 + 𝑏𝑋$, kde $X\sim N(0,1)$. Jaká je hustota pravděpodobnosti $𝑓_𝑌(𝑦)$?
2. Součet dvou [[Statistická závislost a nezávislost|nezávislých]] [[Gaussovo (normální) rozdělení|normálně rozdělených]] náhodných veličin (a naopak?)
3. Jak generovat náhodnou veličinu s [[Cauchyho rozdělení|Cauchyho rozdělení]]?
$$
X = F^{-1}_X, \; kde \; Y \sim U(0,1)
$$

#### Výsledky:
1. $Y \sim N(a,b^2)$
2. $Z = X + Y \quad \sim N(\mu_x + \mu_y,\sigma_x^2 + \sigma_y^2)$
3. $X = \tan (\pi y - \frac 1 2 \pi)$

## Vektorově
Uvažujme [[Vektorová náhodná veličina|náhodnou vektorovou veličinu]] $X = (X_1,...,X_N)^T$, a z ní vytvořme náhodnou veličinu $Y = (Y_1,...,Y_N)^T$ jako $Y=h(X)$.
Nechť $X = (X_1,...,X_N)^T$, je spojitá náhodná veličina, $ℎ ∶ 𝑅^𝑁 → 𝑅^𝑁$ ryze monotónní funkce na množině $X(\Omega)$ a $h^{-1}$ je diferencovatelná a splňuje podmínku:
$$
J = 
\begin{bmatrix}  
\frac{\partial h^{-1}_1}{\partial y_1} & ... & \frac{\partial h^{-1}_1}{\partial y_N}\\   
... & ... & ...\\  
\frac{\partial h^{-1}_{N}}{\partial y_1} & ... & \frac{\partial h^{-1}_{N}}{\partial y_N}  
\end{bmatrix}
\neq 0
$$
Potom náhodná veličina $Y=h(X)$ má hustotu pravděpodobnosti:
$$
f_Y(y) = f_x \left( h^{-1}_1(y), ..., h^{-1}_N(y) \right) |J|
$$
### Příklad:
1. $X,Y \sim N(0,1)$ a jsou nezávislé. Jaká je hustota pravděpodobnosti vektoru $(X-Y,X+Y)$?
2. $X = (X_1,..X_N)^T$ je vektorová náhodná veličina a $Y = AX$, kde $A$ je regulární matice. Jaká je hustota pravděpodobnosti $Y$?