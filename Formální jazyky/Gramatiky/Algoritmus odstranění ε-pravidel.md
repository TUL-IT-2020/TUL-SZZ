# Algoritmus odstranění ε-pravidel
Vstupem je G = (N, T, P, S), výstupem je G’ = (N’, T, P’, S’) 
bez ε-pravidel splňující L (G) = L (G’):
1) Vytvoříme množinu všech neterminálů, které se mohou přímo nebo nepřímo (přepsáním s více kroky) přepsat na prázdný řetězec ε; zapisujeme Nε = {X ∈ N | X ∗ ⇒ ε}. 
2) Zkontrolujeme všechna pravidla P, zda obsahují některý ze symbolů Nε. Pokud ano, do pravidel P’ přidám původní pravidlo znovu bez daného symbolu či skupiny symbolů (simuluji jeho zmizení vlivem ε). Nepřidáváme ale samotná ε-pravidla (X → ε).
3) Jestliže S ∈ Nε, pak do P’ přidáme pravidla S’ → S | ε a do N’ přidáme S’, tj. N’ = N ∪ {S’}. Jestliže S ∉ Nε, pak N’ = N a S’ = S.