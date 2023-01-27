# Hustota pravděpodobnosti
## Absolutně spojité náhodné veličiny
### Definice: 
Náhodná veličina $X$ má absolutně spojité rozdělení (ASR), jestliže existuje nezáporná reálná funkce $𝑓_𝑋(𝑥)$ taková, že pro každé $𝑥 \in 𝑅$ platí:
$$𝐹_𝑋(𝑥) = \int^x_{−\infty} {𝑓_𝑋(𝑡) \; dt}$$ 
Funkci $𝑓_𝑋(𝑥)$ nazýváme **hustotou pravděpodobnosti** náhodné veličiny $X$.

### Základní vlastnosti: 
Pro $X$ mající ASR platí:
$$
𝑓_𝑋(𝑥) = \frac{𝑑𝐹}{𝑑𝑥}(𝑥) 
$$
$$
P[X \in A] = \int_A f_X(x) \; dx 
$$
$$
P[X = a] = 0
$$

### Každá hustota pravděpodobnosti dále splňuje:
$$
𝑓_𝑋(𝑥) ≥ 0
$$
$$
\int^{\infty}_{−\infty} f_X(x) \; dx = 1
$$

## Příklady hustot pro spojité veličiny:
![[Gaussovo (normální) rozdělení]]

![[Uniformní (rovnoměrné) rozdělení]]
![[Zobecněné Gaussovo rozdělení (GGD)]]