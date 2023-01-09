#MVD 
# TF-IDF
V praxi potřebujeme použít počet výskytů. 
TF = **term frequency**, kolikrát se výraz vyskytuje v dokumentu. Problém s TF , pokud se slovo vyskytuje často v každém dokumentu (spojky, předložky, …)
IDF = **inverse document frequency**, v jaké míře se slovo vyskytuje v celé kolekci. Využito k penalizaci častých slov.

P𝑜č𝑒𝑡 𝑠𝑙𝑜𝑣 $𝑊_𝑖$ 𝑣 𝑑𝑜𝑡𝑎𝑧𝑢 $𝑞$:
$$
𝑥_𝑖 = 𝑐 (𝑊_𝑖 , 𝑞) 
$$
P𝑜č𝑒𝑡 𝑠𝑙𝑜𝑣 $𝑊_𝑖$ 𝑣 𝑑𝑜kumentu $d$ modifikováno inverzí frekvence výskytu daného slova:
$$
𝑦_𝑖 = 𝑐(𝑊_𝑖 , 𝑑) × 𝐼𝐷𝐹(𝑊_𝑖) 
$$
Inverzí frekvence výskytu daného slova $W$:
$$
𝐼𝐷𝐹 (𝑊) = \log\left( \frac{𝑀 + 1}{𝑘} \right) 
$$
$M$ = celkový počet dokumentů v kolekci 
$k$ = celkový počet dokumentů obsahující slovo $W$

Výsledná rovnice při použití TF-IDF a počítání relevance pomocí skalárního součinu: 
$$
𝑠𝑖𝑚(𝑞, 𝑑) = \sum^N_{𝑖=1} 𝑥_𝑖𝑦_𝑖 = \sum_{𝑤 ∈ 𝑞 ∩ 𝑑} 𝑐(𝑤, 𝑞) 𝑐(𝑤, 𝑑) \log\left(\frac{𝑀 + 1} {𝑑𝑓(𝑤)} \right) 
$$
$w$ = word (slovo)
$q$ = query (dotaz)
$d$ = document
$M$ = celkový počet dokumentů v kolekci 
$df(w)$ = celkový počet dokumentů obsahující slovo w (document frequency)