# Merge sort (řazení slučováním)
Autor: John von Neuman (1945)
[[Divide and Conquer|D&C]] algoritmus. Větší paměťové nároky – obvykle potřebuje odkládací ADT o velikosti N. Výhody: stabilní, paralelizovatelný, vyšší výkon na sekvenčních médiích. Implicitní řazení v řadě jazyků – např. GNU C a Java.

> [!info] Složitost logaritmická  $O(N*log(N))$ – vždy

### Princip: 
Je opakem QuickSortu, místo dělení posloupnosti slučování pod-posloupnosti, základní myšlenka celého algoritmu – setřídit kratší posloupnost zabere méně kroku, spojit dohromady dvě setříděné posloupnosti tak, aby výsledek byl setřídění, je snadnější než když jsou posloupnosti neseřízené. 

1. Rozdělí neseřazenou množinou dat na dvě podmnožiny o přibližně stejné velikosti
2. Rekurzivně (MergeSortem) setřídíme každou vzniklou podmnožinu
3. Sloučíme obě podmnožiny