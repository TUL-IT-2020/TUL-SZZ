#MVD 
# Word2Vec retrieval model
Porovnání vektoru dotazu a dokumentu. Pomocí [[Kosinová podobnost|kosínové podobnosti]].

Jak tyto vektory vytvořit? Základem je reprezentace slov za pomocí [[Word2Vec]].
- Průměr vektorů slov
	- Stejný problém jako na počátku – jedno četné slovo může ovlivnit výsledek
	- Funguje dobře při velkém množství trénovacích dat 

- Word2Vec v kombinaci s [[TF-IDF|TF-IDF]] vyhlazováním
	- Funguje lépe při menším množství dat 
	- Průměrujeme vážené Word2Vec vektory
	- Váhou každého slova je získané TF-IDF, např.:
$$
𝑞𝑢𝑒𝑟𝑦_{𝑣𝑒𝑐} = \frac{1}{|𝑞|} \sum_{𝑤 ∈ 𝑞} 𝑤𝑜𝑟𝑑2𝑣𝑒𝑐(𝑤) ∗ 𝑡𝑓𝑖𝑑𝑓(𝑤)
$$
$w$ = word (slovo)
$q$ = query (dotaz)
$|𝑞|$ = počet slov v dotazu
