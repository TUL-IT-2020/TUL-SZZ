# Halda
Halda – strom (ADT), který splňuje vlastnost haldy – pokud B je potomek A, pak platí že:
h(A) >= h(B) max-heap
h(A) <= h(B) min-heap
- funkce h(X) udává hodnotu klíče uzlu X
- typ stromu určuje zároveň typ haldy

## Binární halda 
Binární strom, pro který platí:
- vlastnost tvaru – strom je buď vyvážený, nebo se poslední úroveň stromu zaplňuje zleva doprava
- Každý uzel je větší nebo roven svým potomkům

Konstrukce binární haldy je následující:
1. řidáme uzel na spodní úroveň haldy
2. porovnáme přidaný uzel s rodičem, pokud je ve správném vztahu, končíme
3. pokud ne, prohodíme uzel s rodičem a opakujeme předešlý krok.

Maximální počet kroků je tedy roven výšce stromu. Složitost je tedy $O(log(n))$.
Obecně ovšem platí, že cca 50% uzlů jsou listy a cca 75% uzlů se nachází v posledních 2 úrovních, proto také obecně platí, že většina přesunů se uskuteční jen o pár úrovní. Binární halda tedy podporuje vkládání v mnohem rychlejším čase, než je dán složitostí.