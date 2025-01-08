# Konvoluční síť

Zadefinováním konvoluce jako bloku v neurosíti nyní můžeme libovolně kombinovat s ostatními vrstvami.

## Reziduální blok
Podobně jako inception používá složitější bloky. Výstup sestává ze součtu konvoluce a přímo mapovaného vstupu (identity). Síť se tedy učí pouze rezidua:
$$
F(x) = H(x) − x
$$
“Naučit se nuly je jednodušší než identitu”