# Boyer-Moore
hledáme zrcadlově -začínáme na konci P a postupujeme zpět k začátku T. V okamžiku neshody můžeme přeskočit celé skupiny znaků, které se neshodují.

Existují tři situace ve kterých se v okamžiku neshodují.
(`P[j] != T[i]`) nachází vzor:
1. případ – pokud `P` obsahuje `x`, pak zkusíme posunout `P` doprava tak, aby se poslední výskyt `x` dostal proti `x` obsaženému v `T[i]`
2. případ – `P` obsahuje `x`, ale posun doprava na poslední výskyt x není možný, pak posuneme `P` doprava o jeden znak k `T[i+1]`
3. případ – pokud `P` neobsahuje `x`, posuneme `P` tak aby bylo `P[0]` zarovnáno s `T[i+1]`, nejlepší případ – skok o celý vzor
 
## Preprocesing
Stejně jako u KMP i zde určujeme posuny předem analýzou vzorů. Používáme zobrazení všech znaků použité abecedy A do množiny celých čísel. Pro libovolný znak x z A volíme Prep(x) jako největší index pro který platí `P[i] == x` nebo -1 pokud žádný takový index v P neexistuje.

## Časová složitost
> [!info] BM algoritmu je v nejhorším případe: $O(mn + A)$.

Algoritmus je rychlejší pokud je abeceda(A) velká, pomalý pro malou abecedu, tedy stejně jako pro přirozené prohledávání (PP) je vhodný text, špatný pro binární vstupy. BM je rychlejší než PP v případě vyhledávání nad stejnou abecedou.