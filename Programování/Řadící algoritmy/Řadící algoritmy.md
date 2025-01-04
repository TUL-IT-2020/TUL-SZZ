#ALD 
# Řadící algoritmy

$a_1, a_2, ..., a_n$ -> $\pi = ?$ -> $a_{\pi(1)}, a_{\pi(2)}, ..., a_{\pi(n)}$
$a_{\pi(i)} \leq a_{\pi(i+1)}$

D. Knut: The Art of Copmuter Programing, Vol. 3.: Sorting and Searching

## Vlastnosti
> [!summary]
>- *na místě* - pro řazení se nepoužívá žádná další datová struktura (např. další pole)
>- *stabilní* - v seřazené posloupnosti je zachováno pořadí rovnocenných prvků
>- *přirozený* - rychleji zpracuje (částečně) seřazenou množinu, u nepřirozeného to nehraje roli
>- [*interní*](https://en.wikipedia.org/wiki/Internal_sort) - všechna data jsou k dispozici v paměti
>- [*externí*](https://en.wikipedia.org/wiki/External_sorting) - další prvky přichází v průběhu řazení
>- složitost 
 >- [*časová složitost*](https://cs.wikipedia.org/wiki/Asymptotick%C3%A1_slo%C5%BEitost) 
 >- *paměťová složitost*

## Kategorie

- Záměna dvojic po sobě jdoucích prvků mimo pořadí (buble sort, shaker),
- Postupné rozšiřování seřazené části (selection sort, insertion sort),
- [[Rekurzivní algoritmy divide and conquer|Divide and conquer]] (merge sort, quick sort),
- sorting by distribution (k dispozici máme dodatečné informace o rozdělení prvků)

## Rank counting sort
![[Rank counting sort]]

## Radix sort 
![[Radix sort]]
## Bubble sort 
![[Bubble sort]]

## Shaker sort
![[Shaker sort]]

## Comb sort
![[Comb sort]]

## Select sort
![[Select sort]]
## Insert sort
![[Insert sort]]

## Heap sort
![[Heap sort]]

## Merge sort
![[Merge sort]]

## Quick sort
![[Quick sort]]

## Porovnání algoritmů

|**Název**|**Český název**|**Metoda**|**Stabilní**|**Přirozený**|**Složitost**|
|---|---|---|---|---|---|
|BubbleSort|Bublinkové řazení|Záměna|Ano|Ano|O(N2)|
|HeapSort|Řazení haldou|Halda, záměna|Ne|Ne|O(N\*log(N))|
|InsertSort|Řazení vkládáním|Vkádání|Ano|Ano|O(N2)|
|MergeSort|Řazení slučováním|Slučování|Ano|Ano|O(N\*log(N))|
|QuickSort|Rychlé řazení|Záměna|Ne|Ne|O(N2)|
|SelectSort|Řazení výběrem|Výběr|Ne|Ne|O(N2)|
|CombSort|Hřebenové řazení|Záměna|Ne|Ano|O(N2)|
|ShakerSort|Koktejlové řazení|Záměna|Ano|Ano|O(N2)|


| Anglicky       | Česky             | Nejlepší   | Průměrně   | Nejhorší   | Dodatečná pamět | Stabilní  | Přirozené | Metoda    |
|----------------|-------------------|------------|------------|------------|-----------------|-----------|-----------|-----------|
| Selection sort | Řazení výběrem    | O(n²)      | O(n²)      | O(n²)      | O(1)            | zprav. ne | ne        | výběr     |
| Insertion sort | Řazení vkládáním  | O(n)       | O(n²)      | O(n²)      | O(1)            | ano       | ano       | vkládání  |
| Bubble sort    | Bublinkové řazení | O(n)       | O(n²)      | O(n²)      | O(1)            | ano       | ano       | záměna    |
| Merge sort     | Řazení slučováním | O(n log n) | O(n log n) | O(n log n) | O(log n)        | ano       | ano       | slučování |
| Quicksort      | Rychlé řazení     | O(n log n) | O(n log n) | O(n²)      | O(log n)        | ne        | ne        | záměna    |


[Sorting Algorhitm Animations](http://www.sorting-algorithms.com/)
[Rozbor mnoha algoritmu](https://www.algoritmy.net/article/75/Porovnani-algoritmu)