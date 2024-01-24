# Nadbytečné stavy
Konečný automat může mít stavy, ze kterých se není možné dostat do koncového stavu. Takovým stavům říkáme nadbytečné (zbytečné) stavy. Tyto stavy obvykle chceme odstranit, protože pouze komplikují celý KA. Pokud se dostaneme do nadbytečného stavu, tak víme, že vstupní slovo KA nebude přijato. Po odstranění nadbytečných stavů bude automat přijímat stejná slova (automat je ekvivalentní).
Ostatním stavům KA říkáme užitečné. Automat, který neobsahuje žádný nadbytečný Stav, nemusí být ještě minimální (může být dále zjednodušen).

## Hledání nadbytečných stavů
Algoritmus hledání nadbytečných stavů je založen na prohledávání do šířky:
1. Začínáme z množiny koncových stavů (ta je jistě užitečná).
2. Tuto množinu rozšiřujeme o stavy, ze kterých vede orientovaná hrana (šipka) do množiny koncových stavů.
3. Množinu vzniklou v bodě 2 dále rozšiřujeme o stavy, z nichž vede orientovaná hrana do původní množiny.
4. Končíme v případě, že získaná množina se již dále nerozšiřuje.
