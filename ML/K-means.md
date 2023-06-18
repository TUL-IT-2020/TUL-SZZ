#MVD 
# K-means
Pro zvolené číslo 𝐾 se hledá rozklad trénovací množiny na 𝐾 podmnožin (shluků) tak, že každý 𝑗−𝑡ý shluk má svého reprezentanta (centroid) 𝝁𝑗 a je charakterizován součtem vzdáleností mezi ostatními prvky shluku a centroidem. Kritériem vhodnosti rozkladu je součet všech dílčích vzdáleností přes všechny shluky. Toto kritérium se snažíme minimalizovat.

## Algoritmus
Algoritmus je založen na iteračním postupu: 
1. Zvolíme 𝐾 prvků TrM jako prvotní odhady centroidů. 
2. Zařadíme každý prvek TrM do jedné z 𝐾 skupin na základě nejmenší [[Metriky|vzdálenosti]] k centroidu. 
3. Pro každou skupinu vypočteme nový centroid tak, aby měl nejmenší vzdálenost ke všem prvkům skupiny. 
4. Vyhodnotíme celkové kritérium a v případě, že se jeho hodnota liší od předchozí hodnoty o méně než , iterační proces zastavíme, jinak návrat na krok 2.

## Výhody a nevýhody:
### Výhody
Jednoduchý na implementaci a pochopení. Výpočetní náročnost je O(TKN), kde: 
- N je počet dat
- K je počet shluků
- T je počet iterací 
Protože K a T je obvykle malé, je K-means považován za lineární.
Nejpopulárnější algoritmus. Výsledky se obtížně porovnávají, nelze určit nejlepší algoritmus.

### Nevýhody
Není zajištěno dosažení globálního minima kriteriální funkce. Výsledné centroidy mohou záviset na volbě počátečních centroidů. Proces lze opakovat s různými počát. centroidy a vybrat pak to řešení, které má minimální hodnotu kriteriální funkce. Náchylný na přítomnost outlierů. Lze částečně eliminovat. Nefunguje pro všechna rozložení příznaků. Na shlukovaných datech je nutné umět spočítat střední hodnotu. Algoritmus neřeší otázku nejvhodnějšího čísla **K**.

## Potlačení vlivu outlierů
Je možné odstranit data, která jsou nejvíce vzdálená od centroidů. Odstranění je vhodné provádět pouze pokud jsou body vzdáleny ve více iteracích po sobě. Je možné data náhodně navzorkovat – vybrat pro výpočet polohy centroidu jen menší množství bodů. Outlier pak nemusí být vybrán a nemusí negativně ovlivnit výsledek