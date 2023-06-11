#ALD 
# Řadící algoritmy

## Bubble sort (bublinkové řazení, řazení záměnou)
Název od „probublávání“ větších prvků/bublinek na konec (začátek) tříděné množiny.
[[Složitost algoritmů|Složitost]]:
- nejhorší $O(N^2)$, 
- v krajním případě $\frac{(N^2 + N)}{2}$ kroků, 
- nejlepší $O(N)$ – již seřazená. 

přirozená, stabilní, vnitřní

I když má stejnou složitost jako InsertSort je pomalejší – má více elementárních operací v datech. Probublávání v obou směrech se nazývá ShakerSort či CoctailSort – složitost opět $O(N^2)$.

### Princip: 
Pracuje na principu systematického porovnávání dvojice sousedních čísel, pokud menší číslo následuje po větším – výměna, maximální prvek „probublá“ na konec. 
1. Posloupnost rozdělíme na dvě části, setříděnou a nesetříděnou, setříděná část je prázdná
2. Postupně porovnáme všechny sousední prvky nesetříděné části a pokud nejsou v požadovaném pořadí, prohodíme je.
3. Krok 2 opakujeme tak dlouho, dokud nesetříděná část obsahuje více než jeden prvek, jinak algoritmus končí.

## Shaker sort (koktejlové řazení)
Je to vylepšení BubbleSortu. Na rozdíl od BubbleSortu neřadí pouze jedním směrem, ale oběma (zabrání se tak problému želv a zajíců BubbleSortu – vysoké hodnoty probublávají na konec rychlé, ale ty nízké postupují na začátek velmi pomalu). Stejně jako BubbleSort má vnořené cykly – hlavní iterační a vedlejší porovnávací. Hlavní iterační probíhá jen n/2 krát – každá iterace obsahuje dvě fáze:
1. Při dopředené stoupá nejlehčí bublinka vzhůru
2. Při zpětné klesá nejtěžší bublinka ke dnu

Složitost: $O(N^2)$

## Comb sort
Dalším vylepšením BubbleSortu. Opět řeší problém zajíců a želv, ale jinak než ShakerSort. Zavádí snižující se přírůstek (skok), neporovnávají se tedy sousedi, ale prvky vzdálené o tento skok. Při každé iteraci se skok dekrementuje, až je degradován na prostý BS. Díky skoku jsou želvy přesunovány rychleji na správnou stranu. Základem je správná volba skoku. Empiricky dokázáno, že ideální je výpočet skoku jako postupné dělení pole číslem 4/3. Podobný princip využívá i varianta InserSortu – ShellSort.

## Select sort (řazení výběrem)

Velmi jednoduchý algoritmus. Snadná implementace – často se používá pro uspořádání malého množství dat (pro větší množství dat HeapSort nebo MergeSort).

Složitost algoritmu je vždy kvadratická: $O(N^2)$

vnitřní, nepřirozená, nestabilní – může změnit pořadí prvků se stejným klíčem (dáno prohazováním nesousedících prvků)

### Princip: 
Pracuje na principu nalezení minimálního prvku v nesetříděné části posloupnosti a jeho zařazení na konec již setříděné posloupnosti.
1. V posloupnosti najdeme nejmenší prvek a vyměníme ho s prvkem na první pozici
- rozdělení posloupnosti na dvě části – setříděná část obsahuje pouze jeden prvek, nesetříděná n-1
2.  V nesetříděné části najdeme nejmenší prvek
3. Vyměníme ho s prvním prvkem v nesetříděné části
4. dojde k zařazení tohoto prvku do setříděné části
5. Obsahuje-li nesetříděná část více než jeden prvek, pokračujeme bodem 2, jinak je třídění ukončeno.

## Insert sort
Jednoduchá implementace, efektivní na malých množinách. Dokáže řadit data tak, jak přicházejí na vstupu. Efektivní způsob testování, zda jsou data uspořádaná nebo ne.
Složitost: 
- nejhorší O(N2), 
- nejlepší O(N).

vnitřní i vnější, přirozený, stabilní

### Princip: 
Pracuje na principu vkládání prvku na jeho správné místo v posloupnosti, k tomu využívá pomocný prvek, zpravidla nultý prvek posloupnosti.
1. Prvek pole ponecháme na svém místě
2. Vezmeme druhý prvek a porovnáme jej s prvním
- je-li menší, zařadíme ho na první místo a první prvek posuneme
- v opačném případě ponecháme na místě
3. Vezmeme třetí prvek a porovnáme jej s prvními dvěma prvky
- je-li menší než některý z nich, zařadíme jej na odpovídající pozici a následující prvky podle potřeby posuneme
- jinak je ponecháme na původních místech
4. Obdobně postupujeme i s ostatními prvky v poli

## Heap sort (řazení haldou)
Využívá strukturu [[Halda|halda]] pro seřazení prvků. Pro potřeby řazení využijeme binární haldu.
Logaritmická složitost O(N\*log(N)) – vždy
Pokud pro haldu využijeme vstupní pole, nemá HS žádné paměťové nároky navíc. Horší možnosti paralelizace. V průměru pomalejší než QuickSort – ale vhodnější pro rozsáhlé kolekce neznámých dat.

### Princip:
1. Haldy se využívá k tomu, aby se do ní uspořádaly prvky vstupní posloupnosti.
2. Z haldy vybere uzel do výstupní posloupnosti, tzn. Minimální (tedy nejvyšší) uzel (kořen).
3. Následně se provede rekonstrukce haldy ze zbývajících uzlů.
4. Postup se opakuje s tím, že další odebraný uzel (kořen nové haldy) se umístí na začátek výstupní posloupnosti.
5. Výsledkem je setříděná výstupní posloupnost.

## Merge sort (řazení slučováním)
Autor: John von Neuman (1945)
[[Divide and Conquer|D&C]] algoritmus. Větší paměťové nároky – obvykle potřebuje odkládací ADT o velikosti N. Výhody: stabilní, paralelizovatelný, vyšší výkon na sekvenčních médiích. Implicitní řazení v řadě jazyků – např. GNU C a Java.

Složitost logaritmická  $O(N*log(N))$ – vždy

### Princip: 
Je opakem QuickSortu, místo dělení posloupnosti slučování pod-posloupnosti, základní myšlenka celého algoritmu – setřídit kratší posloupnost zabere méně kroku, spojit dohromady dvě setříděné posloupnosti tak, aby výsledek byl setřídění, je snadnější než když jsou posloupnosti neseřízené. 

1. Rozdělí neseřazenou množinou dat na dvě podmnožiny o přibližně stejné velikosti
2. Rekurzivně (MergeSortem) setřídíme každou vzniklou podmnožinu
3. Sloučíme obě podmnožiny

## Quick sort
Autorem je C. A. R. Hooare – 1962. Algoritmus typu rozděl a panuj ([[Divide and Conquer|Divide and Conquer]]). Díky D&C je dobře paralelizovatelný.

vnitřní, nestabilní, nepřirozený

### Pivot
Klíčovým problémem je volba pivota:
- První (poslední) prvek
- Náhodný prvek
- Medián pole, medián 3-5 prvku

Výběr pivota určuje složitost algoritmu: 
- nejhorší $O(N^2)$, 
- nejlepší a průměrný $O(N*log(N))$.

Logaritmickou složitost nelze zaručit, ale reálné aplikace a testy ukazují, že na (pseudo)náhodných datech je vůbec nejrychlejší ze všech obecných řadících algoritmů.

### Princip: 
Pracuje na principu rozdělení pole řazených prvků na dvě části a tyto potom seřadit, využívá rekurzi:
1. Zvolit dělící prvek – pivota, tento je umístěn na konečné pozici.
2. Projdeme pole zleva dokud nenalezneme větší prvek než dělící prvek.
3. Dále ho projdeme zprava dokud nenalezneme menší prvek než dělící prvek.
4. Tyto prvky pak vyměníme.
5. Kroky 2-4 opakujeme až do kompletního setřídění.

## Porovnání algoritmů

|**Název**|**Český název**|**Metoda**|**Stabilní**|**Přirozený**|**Složitost**|
|---|---|---|---|---|---|
|BubbleSort|Bublinkové řazení|Záměna|Ano|Ano|O(N2)|
|HeapSort|Řazení haldou|Halda, záměna|Ne|Ne|O(N\*log(N))|
|InsertSort|Řazení vkládáním|Vkádání|Ano|Ano|O(N2)|
|MergeSort|Řazení slučováním|Slučování|Ano|Ano|O(N\*log(N))|
|QuickSort|Rychlé řazení|Záměna|Ne|Ne|O(N2)|
|SelectSort|Řazení výběrem|Výběr|Ne|Ne|O(N2)|
|CombSort|Hřebenové řazení|Záměna|Ne|Ano|O(N2)|
|ShakerSort|Koktejlové řazení|Záměna|Ano|Ano|O(N2)|

