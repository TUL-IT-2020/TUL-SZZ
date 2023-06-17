# Regrese
## LSE - algebraické řešení
metodou nejmenších čtverců = Least-Squares Estimation
Nevýhodou metody je nutnost počítat inverzi pro ohromné matice (výpočetně náročné, zatížen numerickou chybou).

Polynomiální regrese
```Python
y = theta[0] + theta[1]*x
```

### Chyba
- loss funkce
```Python
L(𝜃) = sum((yi - yni)^2) = sum( (yi - 𝜃[0] - 𝜃[1]*x)^2 )
```

### Učení
Hledáme takovou thetu, aby chyba byla minimální
```Python
𝜃 = (~X^T*~X)^1 * ~X^T*Y
```

## SGD - numerické iterativní
Metoda největšího spádu.
Hrozí najití lokálního minima. Trpí zig-zag efektem pro příliš velký krok alfa.
alfa - velikost kroku

**Momentum**
"Setrvačnost"
Potlačuje oscilace a zrychluje konvergenci.
K aktuálnímu kroku se přidá 90% předchozího. 

### Učení
```Python
# 𝜃 ... theta
# Loss funkce:
L(𝜃) = sum((yn - 𝜃^T*~xn)^2)

# Gradient:
-2*sum((yn - 𝜃^T*~xn)*~xn)

# Algoritmus:
𝜃[t+1] = 𝜃[t] - alfa * sum((yn - 𝜃^T*~xn)*~xn)
```