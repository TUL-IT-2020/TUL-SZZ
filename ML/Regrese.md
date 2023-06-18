#ML 
# Regrese
## LSE - algebraické řešení
[[Bayesovská statistika#Minimum Mean Square Error|MSE?]]
metodou nejmenších čtverců = Least-Squares Estimation 
Nevýhodou metody je nutnost počítat inverzi pro ohromné matice (výpočetně náročné, zatížen numerickou chybou).

Polynomiální regrese
```Python
y = theta[0] + theta[1]*x
```

### Chyba
```Python
L(𝜃) = sum((yi - yni)^2) = sum( (yi - 𝜃[0] - 𝜃[1]*x)^2 )
```

$$
L(\theta) = \sum_{i=1}^{N}(y_i - \hat y_i)^2
$$
- $L$ - Loss funkce
- $\hat y_i$ - predikovaná hodnota

### Učení
Chyba modelu představuje kriteriální funkci. Minimalizovat tuto funkci vzhledem k parametrům modelu znamená najít takové hodnoty parametrů, aby výsledná chyba byla minimální. Najít minimum této funkce znamená vyjádřit její první derivaci vzhledem k hledaným parametrům a položit ji rovnu nule. 
$$
\theta_𝟎 = \overline{𝒚} - \theta_𝟏 * \overline{x} = mean(𝒀) - \theta_𝟏 * mean(X)
$$

Vícenásobná LR (lineární regrese): LSE pro $\theta$
$$
\theta = \left(\widetilde{X}^T*\widetilde{X}\right)^{-1} * \left(\widetilde{X}^T*Y\right)
$$

## SGD
![[SGD - Metoda nejvyššího spádu]]
