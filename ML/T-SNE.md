#MVD 
# t-SNE 
T-distributed Stochastic Neighbor Embedding. Často využíváno pro vizualizaci dat. Redukce dat do 2 nebo 3 dimenzí. 
Dokáže najít i nelineární vztahy mezi daty => Často najde strukturu tam, kde jiné algoritmy ne. 
Intuice => Pokud hodnoty ve vyšší dimenzi spadají do jednoho clusteru -> měly by i v nižší dimenzi 

## Algoritmus
Iterativní algoritmus
1. Výpočet pravděpodobnostního rozdělení hodnot 
	- S jakou pravděpodobností jsou dva body sousedé 
$$
𝑝_{𝑗|𝑖} = \frac{exp( \frac{\Vert𝑥_𝑖 − 𝑥_𝑗\Vert^2}{ 2𝜎_𝑖^2} )} {\sum_{𝑘≠𝑖} exp( \frac{\Vert𝑥_𝑖 − 𝑥_k\Vert^2}{ 2𝜎_𝑖^2} )}
$$
2. Náhodná projekce dat do nižší dimenze a spočteme pro ně studentovo p. rozdělení 
3. Minimalizace KL divergence (jak moc se dvě p. rozdělení liší)

## Paramtery:
- Dimenze výsledného prostoru 
- Perplexita 
	- Použito pro výběr variance Gaussova rozdělení 
	- Často vede k velkým změnám ve výsledné vizualizaci
	- Intuice => Počet sousedů, kteří mají vliv na daný bod
	- Doporučená hodnota 5 až 50
- Learning rate, počet iterací, …