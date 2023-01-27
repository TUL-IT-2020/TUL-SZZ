# Střední hodnota a rozptyl
## DISKRÉTNÍ NÁHODNÁ VELIČINA
### Střední hodnota (Expected value)
$$
E[X] = \sum^n_i{P[X=x_i]}
$$
$$ \mu = \frac{1}{n}\sum^n_i{x_i}$$
### Rozptyl
$$
V[X] = \sum^n_{i=1}{\left( x_i - E[X] \right)^2 P[X=x_i]}
$$
$$ Var(X) = \sum^n_{i=1}{(x_i - \mu)^2} $$

## ABSOLUTNĚ SPOJITÁ NÁHODNÁ VELIČINA
### Střední hodnota
$$
E[X] = \int^\infty_{-\infty} {x \; p(x) \; dx}
$$
### Rozptyl
$$
V[X] = \int^\infty_{-\infty} {\left( x - E[X] \right)^2 \; p(x) \; dx}
$$

Pro střední hodnoty [[Diskrétní náhodné veličiny|diskrétních]] i [[Hustota pravděpodobnosti#Absolutně spojité náhodné veličiny|ASR]] náhodných veličin X,Y a libovolné konstanty $𝑎, 𝑐 ∈ 𝑅$ platí: 
$$
𝐸[𝑎 + 𝑋 + 𝑐𝑌] = 𝑎 + 𝐸[𝑋] + 𝑐𝐸[𝑌]
$$

## Rozptyl
![Variance](https://upload.wikimedia.org/wikipedia/commons/thumb/6/64/Variance_visualisation.svg/300px-Variance_visualisation.svg.png)

Geometric visualisation of the variance of an arbitrary distribution (2, 4, 4, 4, 5, 5, 7, 9):
1.  A frequency distribution is constructed.
2.  The centroid of the distribution gives its mean.
3.  A square with sides equal to the difference of each value from the mean is formed for each value.
4.  Arranging the squares into a rectangle with one side equal to the number of values, $n$, results in the other side being the distribution's variance, $\sigma^2$.

[wiki: Variance](https://en.wikipedia.org/wiki/Variance)