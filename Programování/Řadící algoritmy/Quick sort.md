## Quick sort
Autorem je C. A. R. Hooare – 1962. Algoritmus typu rozděl a panuj ([[Divide and Conquer|Divide and Conquer]]). Díky D&C je dobře paralelizovatelný.

vnitřní, nestabilní, nepřirozený

### Pivot
> [!warning] Klíčovým problémem je volba pivota:
>- **První** (poslední) prvek
>- **Náhodný prvek**
>- **Medián pole**, medián 3-5 prvku

> [!info] Výběr pivota určuje složitost algoritmu: 
>- nejhorší $O(N^2)$, 
>- nejlepší a průměrný $O(N*log(N))$.

> [!warning] 
> Logaritmickou složitost nelze zaručit, ale reálné aplikace a testy ukazují, že na (pseudo)náhodných datech je vůbec nejrychlejší ze všech obecných řadících algoritmů.

### Princip: 
Pracuje na principu rozdělení pole řazených prvků na dvě části a tyto potom seřadit, využívá rekurzi:
1. Zvolit dělící prvek – pivota, tento je umístěn na konečné pozici.
2. Projdeme pole zleva dokud nenalezneme větší prvek než dělící prvek.
3. Dále ho projdeme zprava dokud nenalezneme menší prvek než dělící prvek.
4. Tyto prvky pak vyměníme.
5. Kroky 2-4 opakujeme až do kompletního setřídění.