# Binární vyhledávání
Vyhledávací algoritmus na pricipu **půlení intervalu**.

- Složitost procházení je **O(log2(N))**, tedy lepší (rychlejší) než u lineárního vyhledávání.
- Funguje pouze na **uspořádáném** (seřazeném) seznamu.
- Algoritmus je typu [[Divide and Conquer|divide and conquer]] a možný je rekurzivní i iterativní zápis. (iterativní nevolá funkce a je nepatrně rychlejší)

## Princip: 
(máme pole **p** a prvek **h**)

- Porovnáme prostřední prvek pole p s prvkem h.
- Pokud se rovnají vrátíme ho jako výsledek.
- V případě, že je h menší, musí se hledaný prvek v vyskytovat ve zbytku pole nalevo. (a naopak)
- Tento postup opakujeme (rekurzivně) na zbytkovém poli. (v kódu níže reprezentováno jako zarážky)
- Zbyde-li nám pouze dílčí pole s jedním prvkem a jeho hodnota neodpovídá h, hodnota h se v poli nevyskytuje.

```java
    /**
     * Binarni vyhledavani (rekurzivni zapis)
     * @param array prohledavane pole (setridene od nejvyssiho)
     * @param leftIndex prvni index, na ktery smime sahnout
     * @param rightIndex posledni index, na ktery smime sahnout
     * @param value hodnota k nalezeni
     * @return index hodnoty, -1 v pripade nenalezeni
     */
    public static int binarySearch(int[]  array, int leftIndex, int rightIndex, int value){
        if(leftIndex == rightIndex && array[leftIndex] != value) return -1;

        int middleIndex = leftIndex + (rightIndex - leftIndex)/2;
        if(array[middleIndex] == value) return middleIndex;
        else if(array[middleIndex] > value)
            return binarySearch(array, middleIndex + 1, rightIndex, value);
        else return binarySearch(array, leftIndex, Math.max(leftIndex, middleIndex - 1), value);
}
```