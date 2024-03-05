### KMP (Knouth-Morris-Pratt)
Princip je stejný jako u přirozeného prohledávání. Algoritmus se nikdy nevrací ve vstupním textu – vhodné pro sekvenční zpracování rozsáhlých dat.

Řízení procesu:
- nastupuje pokud se vyskytne neshoda mezi textem a vzorem v pozici `P[j]`
- jaký je největší možný posun vzoru abychom se vyhnuli opakovanému porovnávání

Hledaný největší možný posun je roven délce největšího prefixu `P[0:j-1]`, který je sufixem `P[1:j-1]`.

Chybová funkce:
- protože prefix i sufix hledáme ve vzoru, který známe předem, můžeme celou analýzu prefixů a sufixů provést předem
- označme k jako pozici před neshodou
- chybová funkce (failure function) F(k) je definována jako nejdelší prefix `P[0:k]`, který je také sufixem `P[1:K]`

> [!info] Složitost: $O(m+n)$