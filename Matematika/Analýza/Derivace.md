#Derivace 
# Definice derivace
Derivace je matematická operace, která přiřazuje každému bodu funkce $f$ jinou funkci $f'$, která vyjadřuje okamžitou rychlost změny funkce $f$ v daném bodě. Derivace je tedy funkce, která vyjadřuje rychlost změny funkce $f$ v daném bodě. Derivace funkce $f$ v bodě $x_0$ se značí $f'(x_0)$ nebo $\frac{df}{dx}(x_0)$. 

## Co znamená značení?:
$$
\frac{df(x)}{dx}
$$
- $df(x)$ - změna na y
- $dx$ - změna na x

#TODO doplnit grafem
# Praktický význam derivace
Derivace funkce $f$ v bodě $x_0$ vyjadřuje okamžitou rychlost změny funkce $f$ v bodě $x_0$.

Derivace funkce $f$ v bodě $x_0$ je rovna směrnici tečny funkce $f$ v bodě $x_0$.

Derivace funkce $f$ v bodě $x_0$ je rovna okamžité rychlosti pohybu bodu na křivce $y = f(x)$ v bodě $x_0$.

## Výpočet derivace
Derivace funkce $f$ v bodě $x_0$ se vypočte jako limita podílu přírůstku funkce $f$ a přírůstku argumentu, kdy přírůstek argumentu směřuje k nule.

$$
f'(x_0) = \lim_{h \to 0} \frac{f(x_0 + h) - f(x_0)}{h}
$$

### Derivace některých běžně používaných funkcí

$$
(x^n)' = n \cdot x^{n-1}, \quad n \in \mathbb{R}
$$

$$
(\ln x)' = \frac{1}{x}
$$

$$
(\log_a x)' = \frac{1}{x \cdot \ln a}, \quad a > 0, \ a \neq 1
$$

$$
(e^x)' = e^x
$$

$$
(a^x)' = a^x \cdot \ln a, \quad a > 0
$$

$$
(\sin x)' = \cos x
$$

$$
(\cos x)' = -\sin x
$$

$$
(\tan x)' = \frac{1}{\cos^2 x}
$$

$$
(\cot x)' = -\frac{1}{\sin^2 x}
$$

$$
(\arcsin x)' = \frac{1}{\sqrt{1-x^2}}
$$

$$
(\arccos x)' = -\frac{1}{\sqrt{1-x^2}}
$$

$$
(\arctan x)' = \frac{1}{1+x^2}
$$

$$
(\mathrm{arccot} x)' = -\frac{1}{1+x^2}
$$
### Pravidla pro počítání s derivacemi

$$
(f \pm g)' = f' \pm g' \quad \text{(derivace součtu a rozdílu funkcí)} \\
$$

$$
(f \cdot g)' = f'g + fg' \quad \text{(derivace součinu funkcí)} \\
$$

$$
\left(\frac{f}{g}\right)' = \frac{f'g - g'f}{g^2} \quad \text{(derivace podílu funkcí)} \\
$$

$$
(f(g(x)))' = f'(g(x)) \cdot g'(x) \quad \text{(derivace složené funkce)} \\
$$

$$
\left(f^{-1}(x)\right)' = \frac{1}{f'(f^{-1}(x))} \quad \text{(derivace inverzní funkce)}
$$

### Příklady použití pravidel

$$
(𝑥^7)' = (𝑥^3 \cdot 𝑥^4)' = (𝑥^3)' \cdot 𝑥^4 + 𝑥^3 \cdot (𝑥^4)' = 3 \cdot 𝑥^2 \cdot 𝑥^4 + 𝑥^3 \cdot 4 \cdot 𝑥^3 = 3 \cdot 𝑥^6 + 4 \cdot 𝑥^6 = 7 \cdot 𝑥^6
$$

$$
\left(\frac{𝑥^7}{𝑥^4}\right)' = \frac{(𝑥^7)'\cdot 𝑥^4 - 𝑥^7 \cdot (𝑥^4)'}{(𝑥^4)^2} = \frac{7 \cdot 𝑥^6 \cdot 𝑥^4 - 𝑥^7 \cdot 4 \cdot 𝑥^3}{𝑥^8} = \frac{7 \cdot 𝑥^{10} - 4 \cdot 𝑥^{10}}{𝑥^8} = \frac{3 \cdot 𝑥^{10}}{𝑥^8} = 3 \cdot 𝑥^2
$$

$$
(𝑥^{15})' = (𝑥^3)^5 = 5 \cdot (𝑥^3)^4 \cdot (𝑥^3)' = 5 \cdot 𝑥^{12} \cdot 3 \cdot 𝑥^2 = 15 \cdot 𝑥^{14}
$$

$$
\left(\frac{1}{\sqrt{𝑘\sqrt{𝑥}}}\right)' = \frac{1}{𝑘 \cdot (\sqrt{𝑘\sqrt{𝑥}})^{k-1}} = \frac{1}{𝑘 \cdot 𝑥^{k-1/2}} = \frac{\sqrt{𝑥}}{𝑘 \cdot \sqrt{𝑥}^k} = \frac{1}{k \cdot \sqrt{𝑥}^{k-1}} = \frac{1}{k \cdot (𝑘\sqrt{𝑥})^{k-1/2}} = \frac{1}{\sqrt{𝑘\sqrt{𝑥}}}
$$

$$
(sin^2⁡𝑥)' = (sin⁡𝑥 \cdot sin⁡𝑥)' = (sin⁡𝑥)' \cdot sin⁡𝑥 + sin⁡𝑥 \cdot (sin⁡𝑥)' = cos⁡𝑥 \cdot sin⁡𝑥 + sin⁡𝑥 \cdot cos⁡𝑥 = 2 \cdot sin⁡𝑥 \cdot cos⁡𝑥
$$

$$
\left(\frac{sin⁡𝑥}{cos⁡𝑥}\right)' = \frac{(sin⁡𝑥)' \cdot cos⁡𝑥 - sin⁡𝑥 \cdot (cos⁡𝑥)'}{cos^2⁡𝑥} = \frac{cos⁡𝑥 \cdot cos⁡𝑥 - sin⁡𝑥 \cdot (-sin⁡𝑥)}{cos^2⁡𝑥} = \frac{cos^2⁡𝑥 + sin^2⁡𝑥}{cos^2⁡𝑥} = \frac{1}{cos^2⁡𝑥}
$$

$$
(sin⁡𝑥^2)' = (cos⁡𝑥^2) \cdot (𝑥^2)' = 2 \cdot 𝑥 \cdot cos⁡𝑥^2
$$

$$
(arcsin⁡𝑥)' = \frac{1}{cos⁡(arcsin⁡𝑥)} = \frac{1}{\sqrt{1-𝑥^2}}
$$

$$
(ln⁡𝑥)' = \frac{1}{e^{ln⁡𝑥}} = \frac{1}{𝑥}
$$
