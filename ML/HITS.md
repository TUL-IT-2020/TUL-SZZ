#MVD 
# HITS
Hypertext-Induced Topic Search (HITS). PageRank nijak nerozlišuje autority a huby. Stránky hodnotí pouze dle jejich autority. 
Intuice: 
- Často citované stránky mají dobrou autoritu
- Stránky, které citují hodně jiných stránek jsou dobré huby
Hlavní myšlenka: 
- Dobré autority budou citovány dobrými huby
- Dobré huby odkazují na dobré autority
Např. odkazem na dobrou autoritu zvyšujeme své hub skóre

## Algoritmus
### Počáteční hodnoty: 
$ℎ(𝑑_𝑖) = 1$
$𝑎(𝑑_𝑖) = 1$
$A$ - Matice sousednosti

### Výpočet:
$\vec ℎ = 𝐴 \vec 𝑎$
$\vec a = 𝐴^T \vec h$

Po každé iteraci je potřeba normalizace.