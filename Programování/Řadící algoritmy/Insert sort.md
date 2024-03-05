# Insert sort
Jednoduchá implementace, efektivní na malých množinách. Dokáže řadit data tak, jak přicházejí na vstupu. Efektivní způsob testování, zda jsou data uspořádaná nebo ne.

> [!info] Složitost: 
>- nejhorší $O(N^2)$, 
>- nejlepší $O(N)$.

> [!done] vnitřní i vnější, přirozený, stabilní

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