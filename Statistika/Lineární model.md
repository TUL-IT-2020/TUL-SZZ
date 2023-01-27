# Lineární model
## Základní lineární model
Mějme model náhodné veličiny:
$$
X_i = A + Bi + w_i
$$
- $i=1,...,N$
- $A$, $B$ jsou neznámé parametry, které chceme odhadnout
- $w_i \sim N(0, \sigma^2)$

Takový model nazveme lineární a lze jej zapsat ve tvaru:
$$
x = H\theta + w
$$
- $\theta = [A,B]^T$
- $$
H = \begin{bmatrix}  
1 & 1 \\   
... & ...\\  
1 & N  
\end{bmatrix}
$$
- $w_i \sim N(0, \sigma^2)$

### Odhady parametrů základního lineárního modelu
Best linear unbiased estimator.
Mějme model náhodné veličiny:
$$
x = H\theta + w
$$
Kde $𝒙$ je $𝑁 × 1$ vektor pozorování, $\theta$ je $𝑝 × 1$ odhadovaný vektor parametrů , $H$ je známá matice $𝑁 × 𝑝(𝑁 > 𝑝)$, a $W$ je $𝑁 × 1$ vektor šumu, tedy $w \sim N(0, \sigma^2 I)$. 

Pak odhad s minimálním rozptylem je:
$$
\hat \theta = \left( H^TH \right)^{-1} H^Tx
$$
a navíc kovarianční matice odhadu $\hat \theta$: 
$$
cov(\hat \theta) = \sigma^2 \left( H^TH \right)^{-1}
$$
Pro lineární modely se dokonce jedná o eficientní odhad (dosahuje [[Rao-Cramérova dolní mez|CRLB]]) a je tedy nejlepší [[Teorie odhadů#Kvalita odhadu|nestranný]] (best linear unbiased estimator = **BLUE**).

## Obecný lineární model
Mějme model náhodné veličiny:
$$
x = H\theta + s + w
$$
Kde $x$ je $𝑁 × 1$ vektor pozorování, $\theta$ je $𝑝 × 1$ odhadovaný vektor parametrů, $H$ je známá $𝑁 × 𝑝$ matice $(N > p)$ , $s$ je $N × 1$ známý signál a $w$ je $𝑁 × 1$ vektor šumu, kde $w \sim N(0,C)$.

Pak odhad s minimálním rozptylem je:
$$
\hat \theta = \left( H^T C^{-1} H \right)^{-1} H^T C^{-1}(x-s)
$$
a navíc kovarianční matice odhadu $\hat \theta$: 
$$
cov(\hat \theta) = \sigma^2 \left( H^T C^{-1} H \right)^{-1}
$$
Pro lineární modely je odhad opět eficientní (dosahuje CRLB) a je tedy nejlepší nestranný.