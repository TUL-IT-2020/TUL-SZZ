#uzo
# Barvení objektu 
U této metody se obraz prochází po řádcích. Každému nenulovému obrazovému elementu $f(i, j)$ se přiřadí hodnota podle hodnoty jeho sousedních element, pokud sousední elementy existují. Algoritmus pro barvení objekt lze popsat následujícími kroky: 

1. **První průchod**: 
Obraz se prochází po řádcích dokud není nalezen obrazový element $f(i, j)$. Každému nenulovému obrazovému elementu $f(i, j)$ se přiřadí hodnota podle hodnoty jeho sousedních element, pokud sousední elementy existují (poloha soused je dána maskou v tabulce. Všechny sousední elementy dané maskou již byly v předchozích krocích obarveny. 
- Jsou-li všechny sousední elementy částí pozadí (mají nulovou hodnotu), přiřadí se obrazovému elementu dosud nepřidělená hodnota (barva). 
- Má-li práv jeden ze sousedních element nenulovou hodnotu, přiřadí se obarvovanému elementu hodnota tohoto sousedního elementu. 
- Je-li nenulových více sousedních obrazových element, přiřadí se obarvovanému elementu hodnota kteréhokoli nenulového obrazového elementu ze zkoumaného okolí. Jestliže nebyly hodnoty sousedních element různé (tzv. kolize barev), zaznamená se ekvivalentní dvojice do tabulky ekvivalence barev. 

2. **Druhý průchod**: 
Po průchodu celého obrazu jsou všechny obrazové elementy náležející oblastem obarveny, některé oblasti jsou však obarveny více barvami (kolize barev). Proto se obraz projde po řádcích ještě jednou a podle informace o ekvivalenci barev se přebarví obrazové elementy dané oblasti. Každé oblasti odpovídá označení (obarvení) jedinou, v jiné oblasti se nevyskytující hodnotou (barvou). 

Maska barvení pro 8-okolí:
$$
\begin{vmatrix}
(i – 1, j – 1) & (i, j – 1) & (i + 1, j – 1) \\\
(i – 1, j) & (i, j) & (i + 1, j)  \\\
(i – 1, j + 1) & (i, j + 1) & (i + 1, j + 1)
\end{vmatrix} 
$$

Zdroj:
https://is.muni.cz/th/255824/fi_b_a2/Stastny.pdf