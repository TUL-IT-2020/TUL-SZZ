#ALD 
# Složitost algoritmů
Rozdělení problémů:
- řešitelné (solvable) 
- neřešitelné (nonsolvable)

Neřešitelné:
- halting problém
	- zastaví se Turingův stroj?

Řešitelné úlohy:
- snadno řešitelné (tractable)
- obtížně řešitelné (intractable)

Složitost algoritmů:
- paměťová složitost
- časová složitost

Časová složitost:
- Chování v nejhorším případě (worst case analysis)
- Chování v průměrném čase (average case analysis)

## Co nás zajímá?
V praxi je důležité umět mezi sebou porovnat algoritmy řešící stejný problém.

- Máme funkci $f(n)$ a snažíme se popsat její asymptotické chování.
- Časová složitost se také označuje jako asymptotická složitost.
- Kromě časové složitosti se někdy určuje i paměťová náročnost.
- Používá se symbolika:
  - $O$ ... velké O
  - $\Omega$ ... velké omega
  - $\Theta$ ... velké theta
- ![f: \mathbb{N} \rightarrow \mathbb{R}^+](https://latex.codecogs.com/svg.latex?f%3A%20%5Cmathbb%7BN%7D%20%5Crightarrow%20%5Cmathbb%7BR%7D%5E&plus;)
- ![g: \mathbb{N} \rightarrow \mathbb{R}^+](https://latex.codecogs.com/svg.latex?g%3A%20%5Cmathbb%7BN%7D%20%5Crightarrow%20%5Cmathbb%7BR%7D%5E&plus;)

### Rostou pomaleji
$$
O(g(n)) = 
\{
f(n) | \exists K > 0 \exists \; n_0 \; \forall n \ge n_0 \;
f(n) \le Kg(n)
\}
$$
Množina funkcí, které až na kladnou multiplikativní konstantu nerostou rychleji než $g(n)$.

### Rostou rychleji
$$
\Omega(g(n)) = 
\{
f(n) | \exists K > 0 \exists \; n_0 \; \forall n \ge n_0 \;
Kg(n) \le f(n)
\}
$$
Množina funkcí, které až na kladnou multiplikativní konstantu rostou alespoň tak rychle jako $g(n)$.

### Rostou stejně rychle
$$
\theta(g(n)) = 
\{
f(n) | \exists K_1,K_2 > 0 \exists \; n_0 \; \forall n \ge n_0 \;
K_1g(n) \le f(n) \le K_2g(n)
\}
$$
Množina funkcí, které až na kladnou multiplikativní konstantu rostou rychle jako $g(n)$.

### Algoritmy lze porovnat pomocí:
- Časové složitosti
	- Doba výpočtu daného algoritmu potřebná pro zpracování daného objemu dat.
	- Složitost neměří v sekundách, ale počtem provedených operací, přičemž trvání jedné operace je bezrozměrná jednotka.
- Paměťová složitosti
	- Velikost paměti využívané při výpočtu (prostorová)

## FLOPS
> [!tip] FLOPS (Floating Point Operations Per Second) 
> – oblíbená metrika výkonu počítačů.

## Asymptotická složitost algoritmu 
Každému algoritmu lze jednoznačně přiřadit rostoucí funkci zvanou asymptotická složitost, která charakterizuje počet operací algoritmu v závislosti na rostoucím rozsahu vstupních dat (čím pomaleji tato funkce roste, tím je algoritmus rychlejší). Skutečná složitost závisí na složitosti implementace daného problému a na počítači na kterém je prováděn (složitost se obecně nedá spočítat) – abychom tento problém vyřešili, začali se používat odhady složitosti – růst složitosti vzhledem ke zvětšujícím se vstupům -> asymptotická složitost.

Složitost algoritmu A je řád růstu funkce f(N), která charakterizuje počet elementárních operací algoritmu A při zpracování dat o rozsahu N. U většiny algoritmů nezáleží na tom zda počítáme všechny operace, či pouze operace nebo porovnání v datech, složitost vychází stejná. 

Rozdělení algoritmů do tříd složitostí, o kterých platí, že od určitého množství dat, je algoritmus vždy pomalejší/rychlejší.
Obvykle místo asymptotické složitosti algoritmu říkáme pouze složitost algoritmu. V podstatě nás zajímá pouze nejdůležitější členy funkce (O notace konstanty a méně významné členy požere) (není důležité jak moc je lineární funkce nakloněná, protože ji kvadratická stejně jednou předežene).

Správný zápis:
$$
f(n) \in 0(g(n))
$$

### Počítání složitosti 
Celkový počet elementárních operací, případně počet elementárních operací nad daty (elementární operace - aritmetické operace, porovnání dvou čísel, přesun čísla v paměti ...) nebo i počet porovnání – všechny tyto metody dávají obvykle tentýž výsledek. 

### Řád funkce 
Řád růstu funkce f je taková „co nejjednodušší“ funkce g, pro kterou platí, že f je asymptoticky ohraničená funkcí g z obou stran (až na konstantu). Řád funkce určíme tak, že zanedbáváme aditivní členy rostoucí pomaleji nebo stejně rychle a multiplikativní konstantu

![[Slozitost_programu.png]]
## O-notace 
> [!example] Obvyklý zápis složitosti algoritmu:
>-	$O(1)$ – konstantní – indexování prvku v poli
>-	$O(log(N))$ – logaritmická
>-	$O(log_2(N))$ – vyhledávání prvku v seřazeném poli metodou půlení intervalu
>-	$O(N)$ – lineární – vyhledávání prvku v neseřazeném poli lineárním vyhledáváním
>-	$O(N*log(N))$ – lineárně-logaritmická – seřazení pole reálných čísel podle velikosti ([[Merge sort|Mergesort]])
>-	$O(N^2)$ – kvadratická – DFT
>-	$O(N^3)$ – kubická
>- $O(N^X)$ – polynomiální  
>- $O(2^N)$ – exponenciální
>- $O(2^N)$ – přesné řešení problému obchodního cestujícího
>- $O(N!)$ – faktoriálová

> [!done] Porovnání složitostí:
$$
1 \ll log(n) \ll n \ll n*log(n) \ll n^k \ll k^n \ll n! \ll n^n
$$

## Amortizovaná složitost (AMS)
Určuje časovou složitost jako průměr v sekvenci nejhorších případů (v sekvenci nejhorší možných vstupních dat). Na rozdíl od průměrované nevyužívá pravděpodobnost a je zaručená. Paradoxně může mít lepší průběh než asymptotická (ASS). 
Algoritmy s vysokou ASS často mění strukturu samotných dat, to se samozřejmě promítá do časové složitosti, potom se špatný případ nestane dlouhou dobu – nastane jeho amortizace (například u dynamického pole). Dává přesnější popis dlouhodobého chování systému.

## Porovnání složitostí

V tabulce seřazeno od nejrychlejší po nejnáročnější.

| Notace                        | Název         | Příklad algoritmu                                         |
| ----------------------------- | ------------- | --------------------------------------------------------- |
| $\mathcal{O}(1)$              | konstantní    | nalezení prvku v hashovací tabulce                        |
| $\mathcal{O}(\log n)$         | logaritmická  | vyhledání prvku metodou půlení intervalu v seřazeném poli |
| $\mathcal{O}(n)$              | lineární      | vyhledání prvku v neseřazeném poli                        |
| $\mathcal{O}(n \cdot \log n)$ | linearitmická | merge sort                                                |
| $\mathcal{O}(n^2)$            | kvadratická   | řazení pole výběrem                                       |
| $\mathcal{O}(n^3)$            | kubická       | násobení matic                                            |
| $\mathcal{O}(2^n)$            | exponenciální |                                                           |
| $\mathcal{O}(n!)$             | faktoriálová  | problém obchodního cestujícího hrubou silou               |
| $\mathcal{O}(n^n)$            |               |                                                           |


## Úlohy P, NP, NP-úplné

[Video na youtube](https://www.youtube.com/watch?v=YX40hbAHx3s)

Typy úloh:
- P,
- NP,
- NP-úplné

![[P,NP,NPC.jpg]]

### 1. Úlohy P (polynomial time)
> [!tip] Úlohy řešitelné v polynomiálním čase $\mathcal{O}(f(n)) \subset \mathcal{O}(n^k)$

Například:
- Násobení
- Řazení

### 2. Úlohy NP (non-deterministic polynomial time)
> [!tip] Úlohy, jejichž řešení lze ověřit v polynomiálním čase.

Patří sem všechny úlohy z P, ale kromě toho i další, které už nepatří do P, 

Například:
- Faktorizace - rozklad na prvočísla (asymetrická kryptografie)
- Návrh desek plošných spojů
- Problém obchodního cestujícího

### 3. Úlohy NP-úplné
Jsou úlohy, které jsou NP, nejsou P a *lze na ně převést všechny ostatní NP úlohy*.
Pokud by se našlo řešení NP-úplné úlohy, které by bylo schopné řešit danou úlohu v polynomiálním čase, znamenalo by to, že $P = NP$ (všechny NP úlohy bychom dokázali vyřešit v polynomiálním čase)
Konsenzus je, že $P \neq NP$, ale zatím to nebylo dokázáno (jedná se o jeden z [Millenium Prize Problems](https://en.wikipedia.org/wiki/Millennium_Prize_Problems))

