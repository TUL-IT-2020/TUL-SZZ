# Lineární vyhledávání
Postupné sekvenční procházení prvků seznamu od začátku do konce, známe také jako **sekvenční vyhledávaní**.

Složitost vyhledávání je $O(N)$:
- Nejlepší je $O(1)$, je-li prvek na první pozici.
- Průměrně pak $O(N/2)$.
- Nejhorší $O(N)$, je-li prvek na poslední pozici.

- Na rozdíl od binárního vyhledávání lze použít na **neuspořádaný** (neseřazený) seznam.
- V některých případech jde o jediný možný způsob prohledávání (spojový seznam).

## Princip: 
(máme pole **p** a prvek **h**)

- Porovnáme první prvek pole p s prvkem h.
- Pokud se rovnají vrátíme index prvku jako výsledek.
- V opačném případě posuneme ukazatel a porovnáme další prvek z p s prvkem h.
- Tento postup opakujeme, dokud nenajdeme požadovanou hodnotu nebo nedorazíme na konec pole.
- Jsme-li na konci a žádný prvek nyvyhověl h, tak se v poli požadovaná hodnota nenachází.

```java
/**
  * Linearni vyhledavani
  * @param array pole, ve kterem hledame
  * @param value hodnota, kterou hledame
  * @return index hledaneho prvku, -1 v pripade nenalezeni
  */
 public static int linearSearch(int[] array, int value){
     for(int i = 0; i < array.length; i++){
         if(array[i] == value) return i;
     }
     return -1;
 }
```