# Heap sort (řazení haldou)
Využívá strukturu [[Halda|halda]] pro seřazení prvků. Pro potřeby řazení využijeme binární haldu.

> [!info] Logaritmická složitost $O(N*log(N))$ – vždy

> [!tip] 
> Pokud pro haldu využijeme vstupní pole, nemá HS žádné paměťové nároky navíc. 

Horší možnosti paralelizace. V průměru pomalejší než QuickSort – ale vhodnější pro rozsáhlé kolekce neznámých dat.

### Princip:
1. Haldy se využívá k tomu, aby se do ní uspořádaly prvky vstupní posloupnosti.
2. Z haldy vybere uzel do výstupní posloupnosti, tzn. Minimální (tedy nejvyšší) uzel (kořen).
3. Následně se provede rekonstrukce haldy ze zbývajících uzlů.
4. Postup se opakuje s tím, že další odebraný uzel (kořen nové haldy) se umístí na začátek výstupní posloupnosti.
5. Výsledkem je setříděná výstupní posloupnost.