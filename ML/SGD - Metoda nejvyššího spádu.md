#ML
# SGD - Metoda nejvyššího spádu
Metoda největšího spádu. Numerické iterativní řešení.
Hrozí najití lokálního minima. Trpí zig-zag efektem pro příliš velký krok alfa.

$$
𝑥_{𝑡+1} = 𝑥_𝑡 − \alpha \frac{𝑑}{𝑑𝑥} 𝐿(𝑥_𝑡)
$$
- $\alpha$ - (alfa) velikost kroku

## Zig-zag
Efekt nastává, pokud je optimální směr konvergence kolmý na gradient. Konvergence pak probíhá směrem k minimu ale dochází k oscilaci.

## Další metody:
### momentum
"Setrvačnost"
Potlačuje oscilace a zrychluje konvergenci. K aktuálnímu kroku se přidá 90% předchozího. 

### adagrad

## Učení
```Python
# 𝜃 ... theta
# Loss funkce:
L(𝜃) = sum((yn - 𝜃^T*~xn)^2)

# Gradient:
-2*sum((yn - 𝜃^T*~xn)*~xn)

# Algoritmus:
𝜃[t+1] = 𝜃[t] - alfa * sum((yn - 𝜃^T*~xn)*~xn)
```

## Zdroje:
- [Gradient descent, how neural networks learn | Chapter 2, Deep learning](https://www.youtube.com/watch?v=IHZwWFHWa-w)