#MVD 
# DBSCAN
Density-Based Spatial Clustering Algorithm
Shluk je definován jako maximální množina hustě spojených bodů. Dva parametry: 
- Epsilon (Eps) - Radius okolo bodu 
- MinPts - Minimální počet bodů v okolí Eps 

$Eps$ okolí bodu $q$: $𝑁_{𝐸𝑝𝑠}(𝑞) = \{𝑝\ 𝑝𝑎𝑡ří\ 𝑑𝑜\ 𝐷\ |\ 𝑑(𝑝, 𝑞) ≤ 𝐸𝑝𝑠\}$

-  **Přímá dosažitelnost**
Bod p je přímo dosažitelný z bodu q, pokud: 
$p$ patří do $𝑁_{𝐸𝑝𝑠}(𝑞)$ (bod p patří do okolí bodu q) 
$| 𝑁_{𝐸𝑝𝑠}(𝑞) | ≥ 𝑀𝑖𝑛𝑃𝑡𝑠$ (bod q je core bod) 
- **Nepřímá dosažitelnost**
Bod $p$ je nepřímo dosažitelný z bodu $q$, pokud existuje řada bodů 𝑝1 , … , 𝑝𝑛 (𝑝1 = 𝑞, 𝑝𝑛 = 𝑝) taková, že pi+1 je přímo dosažitelný z pi.
- **Propojenost**
Body $p$ a $q$ jsou propojené, pokud existuje bod o, ze kterého jsou oba body ($p$ a $q$) nepřímo dosažitelné

## Algoritmus
1. Vybrat počáteční bod p 
2. Získat všechny nepřímo dosažitelné body 
	a) Pokud je bod p core bod -> cluster hotový 
	b) Pokud je p border bod, tak z něj ostatní body nemohou být nepřímo dosažitelné -> vybrat další počáteční bod z databáze 
3. Pokračujeme, dokud jsme neprošli všechny body