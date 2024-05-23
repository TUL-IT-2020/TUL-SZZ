# Vícerozměrné normální rozdělení
Sdružená hustota pravděpodobnosti náhodné [[Vektorová náhodná veličina|vektorové veličiny]] $X = (X_1, ..., X_n)^T$ mající [[Gaussovo (normální) rozdělení|Normální rozdělení]]:
$$
f_X(x) = \frac{1}{(2\pi)^{\frac{N}{2}} \left(det(\Sigma)\right)^{\frac{1}{2}}} e^{-\frac{1}{2} (x-\mu)^T\Sigma^{-1}(x-\mu)}
$$
$\mu = (\mu_1, \mu_2, ..., \mu_N)^T = E[(X_1,X_2,...,X_N)^T]$
$\Sigma = E[(X-\mu)(X-\mu)^T]$

Pro vektor dimenze 2 je pak hustota:
$$
f_{X,Y}(x,y) = \frac{1}{2\pi} \frac{1}{\sqrt{det(\Sigma)}} e^{-\frac{1}{2} (x-\mu)^T\Sigma^{-1}(x-\mu)}
$$
$$
\Sigma 
= \begin{pmatrix}
E[(X-\mu_x)^2] & E[(X-\mu_x)(Y-\mu_y)]\\\ 
E[(X-\mu_x)(Y-\mu_y)] & E[(Y-\mu_y)^2]
\end{pmatrix} 
= \begin{pmatrix}
\sigma^2_x & p\sigma_x\sigma_y\\\ 
p\sigma_x\sigma_y & \sigma^2_y
\end{pmatrix}
$$
