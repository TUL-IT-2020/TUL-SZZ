# Select sort (řazení výběrem)

Velmi jednoduchý algoritmus. Snadná implementace – často se používá pro uspořádání malého množství dat (pro větší množství dat HeapSort nebo MergeSort).

> [!info] Složitost algoritmu je vždy kvadratická: $O(N^2)$

vnitřní, nepřirozená, nestabilní – může změnit pořadí prvků se stejným klíčem (dáno prohazováním nesousedících prvků)

### Princip: 
Pracuje na principu nalezení minimálního prvku v nesetříděné části posloupnosti a jeho zařazení na konec již setříděné posloupnosti.
1. V posloupnosti najdeme nejmenší prvek a vyměníme ho s prvkem na první pozici
- rozdělení posloupnosti na dvě části – setříděná část obsahuje pouze jeden prvek, nesetříděná n-1
2.  V nesetříděné části najdeme nejmenší prvek
3. Vyměníme ho s prvním prvkem v nesetříděné části
4. dojde k zařazení tohoto prvku do setříděné části
5. Obsahuje-li nesetříděná část více než jeden prvek, pokračujeme bodem 2, jinak je třídění ukončeno.