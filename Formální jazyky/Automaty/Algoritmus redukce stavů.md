# Algoritmus redukce stavů
Algoritmus vychází z toho, že se v automatu vyskytují dvě jistě neekvivalentní množiny stavů – koncové (výstupní) a ostatní. Tyto množiny pak postupně rozdělujeme pomocí zkoumání, jaká je jejich přechodová funkce. Předpokládejme deterministický KA (může být úplný i neúplný).

1. Na začátku rozdělíme tabulku přechodů do dvou skupin (tříd, množin) – jedna jsou koncové stavy, druhá část ostatní stavy. Postupně procházíme stavy automatu a pro jednotlivé prvky abecedy zjišťujeme, ve které skupině se nachází stav, do kterého se při přechodu dostaneme. Číslo této skupiny zapíšeme do tabulky k prvku abecedy u řešeného stavu.
2. Tabulku opět rozdělíme do skupin, v každé části necháme stavy, ze kterých se pod všemi prvky abecedy dostaneme do stejných skupin tabulky. Aplikujeme předchozí krok. 
3. Zmíněný postup aplikujeme, dokud každá skupina tabulky neobsahuje pouze stavy přecházející do stejných skupin (při daném vstupním symbolu). Ve výsledné tabulce nezapisujeme názvy stavů, ale jen označení skupin a jejich přechody.

Principem algoritmu je, že testujeme přechodovou funkci na řetězce délky 0, 1, 2,… Jsou-li dva stavy ekvivalentní, musí být ekvivalentní na všechny délky řetězců (∼0, ∼1, ∼2,… ∼k = ∼ ), tedy pro:
$$
q_1,q_2 \in Q : q_1 \sim_0 q_2 : q_1 \in F \iff q_2 \in F
$$
$$
q_1 \sim_{i+1} q_2 : q_1 \sim_i q_2 ∧ \forall a \in \Sigma : \delta(q1, a) \sim_i \delta(q_2, a) 
$$

Řetězců sice může být obecně nekonečné množství, ale postup se díky konečnému počtu stavů a smyčkám v nich „ustálí“ (ukončí).