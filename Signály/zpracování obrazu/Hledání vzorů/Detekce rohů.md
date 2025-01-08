# Detekce rohů
Roh = místo, kde se potkávají dvě hrany

## Jak poznáme roh?
Obraz lze rozdělit na různé případy:
- plochá oblast: textura okna se s jeho pohybem nemění,
- hrana: textura okna se s pohybem podél hrany nemění,
- roh: textura okna se změní při jakémkoliv pohybu.

Změna textury v závislosti na pohybu okna:
- plochá oblast: textura okna se s jeho pohybem nemění 
- hrana: textura se mění pouze při pohybu “proti” hraně 
- roh: textura okna se změní při jakémkoliv pohybu

## Moravcův detektor rohů (1980)
Pouze 4 offsety $(Δ𝑥, Δ𝑦)$: 
1. $𝑒1 = \sum_{𝑥,𝑦} (𝐼(𝑥 + 1, 𝑦) − 𝐼(𝑥, 𝑦)^2)$ 
2. $𝑒2 = \sum_{𝑥,𝑦} (𝐼(𝑥 + 1, 𝑦 + 1) − 𝐼(𝑥, 𝑦)^2)$
3. $𝑒3 = \sum_{𝑥,𝑦} (𝐼(𝑥, 𝑦 + 1) − 𝐼(𝑥, 𝑦)^2)$
4. $𝑒4 = \sum_{𝑥,𝑦} (𝐼(𝑥 − 1, 𝑦 + 1) − 𝐼(𝑥, 𝑦)^2)$ 

Roh je nalezen, pokud:
$$
min(𝑒1, 𝑒2, 𝑒3, 𝑒4) ≥ 𝑇 
$$
> [!missing] Nedostatky: 
> - Citlivost na šum 
> - Pouze 4 směry 
> - Není izotropický → při “nesprávném” natočení hrany detekuje jako roh