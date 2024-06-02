# Indexy
Předtřídění podle atributu.
Urychlí vyhledávání, ale mohou dramaticky zpomalit vkládání (nutnost přeorganizovat pomocné indexy).

> [!tip] 
> Primární a cizí klíč jsou dobré kandidáty na vytvoření indexu.
## Druhy indexů
- Stromy a vyhledávání nad nimi. 
> [!warning]
>- Záznamy jsou uložené až v listech! 
>- Ostatní vrcholy grafu jsou jen rozcestí!

- [[Stromy|Stromy]]
	- ISAM, statické,
	- B+, dynamické,
	- [[R-stromy]],
- [[Hashovaní|Hash-mapy]]
	- Statické, při kolizi -> lineární seznam/heap/setříděný seznam,
	- Dynamické, 
		- přehešování všech záznamů,
		- víceúrovňová hash funkce,
		- využití globální a lokální hloubky s dynamickým rozšířením.
- Indexy s [[Bitová mapa|bitovou mapou]]
	- přidání sloupce "one-hot-encoding".

### Porovnání Indexů dle druhu:

| Operace | Stromy | Hash |
| ------- | ------ | ---- |
| =       | +      | +    |
| >, <    | +      | -    |
## Typ indexu
Neklastrovaný index (ukazatele indexu mají pointry do paměti)
- můžeme mít více různých indexů nad jednou tabulkou.
Klastronavý index (data v indexu jsou seřazena stejně jako v databázi)
- výrazně rychlejší u dotazů na rozsah

![[Typ indexu]]
### Porovnání indexů dle typu:

| operace        | cluster index | uncluster index |
| -------------- | ------------- | --------------- |
| >, <           | +             | -               |
| INSERT, UPDATE | -             | +               |
> [!tip] UNIQUE atribut
> Urychluje vyhledávání, stačí nám najít jen první schodu v databázi.

## Optimalizace databázových struktur podrobněji
![[Optimalizace databázových struktur]]