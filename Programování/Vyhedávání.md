#ALD
# Vyhledávání

## Lineární vyhledávání
Postupné sekvenční procházení prvků seznamu od začátku do konce, známe také jako **sekvenční vyhledávaní**.

Složitost vyhledávání je $O(N)$:
- Nejlepší je $O(1)$, je-li prvek na první pozici.
- Průměrně pak $O(N/2)$.
- Nejhorší $O(N)$, je-li prvek na poslední pozici.

- Na rozdíl od binárního vyhledávání lze použít na **neuspořádaný** (neseřazený) seznam.
- V některých případech jde o jediný možný způsob prohledávání (spojový seznam).

### Princip: 
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

## Binární vyhledávání

Vyhledávací algoritmus na pricipu **půlení intervalu**.

- Složitost procházení je **O(log2(N))**, tedy lepší (rychlejší) než u lineárního vyhledávání.
- Funguje pouze na **uspořádáném** (seřazeném) seznamu.
- Algoritmus je typu [[Divide and Conquer|divide and conquer]] a možný je rekurzivní i iterativní zápis. (iteratívní nevolá funkce a je nepatrně rychlejší)

### Princip: 
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

## Datové struktury optimalizované pro vyhledávání

### Binární vyhledávací strom (BST)

Datová struktura založená na binárním [[Stromy|stromu]], v němž jsou jednotlivé prvky (uzly) uspořádány tak, aby v tomto stromu bylo možné rychle vyhledávat danou hodnotu.

- Postaveno na principu binárního vyhledávání. (vyvážený BST strom má složitost vyhledávání O(log2(N))
- Jedná se o binární strom, každý uzel tedy má nanejvýš dva potomky − levého a pravého.
- Každému uzlu je přiřazen určitý klíč. Podle hodnot těchto klíčů jsou uzly uspořádány.
- Levý podstrom uzlu obsahuje pouze klíče menší než je klíč tohoto uzlu.
- Pravý podstrom uzlu obsahuje pouze klíče větší než je klíč tohoto uzlu.
- Může (multimnožina) i nemusí (množina) podporovat duplicitní hodnoty. (ostrá a neostrá nerovnost, záleží na implementaci)
- Základ pro konstrukci abstraktnějších datových struktur jako jsou množiny, multimnožiny a asociativní pole.

![Binární vyhledávací strom](30_bst.png)

_Binární vyhledávací strom_

**Operace**

Všechny operace na binárním stromě opakovaně porovnávají hodnoty klíčů. Může se jednat o triviální porovnání dvou čísel či řetězců, ale také o složitější podprogram, pokud úlohu klíče hraje kombinace několika datových položek uzlu. Kromě klíče uzel zpravidla nese další datové položky, které tvoří vlastní obsah datové struktury. Operacemi vzniká problém s vyvážením, proto byl tvořen samovyvažovací strom (**AVL**), který tyto problémy řeší automaticky.

_Vyhledávání_

Vyhledání konkrétní hodnoty v binárním vyhledávacím stromu typicky probíhá rekurzivně. Začíná zpravidla v kořeni. V každém kroku porovná hledanou hodnotu s klíčem zkoumaného uzlu. Pokud jsou si rovny, hodnota byla nalezena. Je-li hledaná hodnota menší, pokračuje hledání v levém podstromu. Je-li větší, bude hledání pokračovat v pravém podstromu. Díky uspořádání stromu je cesta k hledané hodnotě jednoznačně určena.

_Přidání uzlu_

Vložení nového uzlu začíná hledáním jeho pozice ve stromu – postupuje se stejně jako při vyhledávání, jako hledaná hodnota se použije klíč vkládaného uzlu. Tato fáze může vést ke dvěma různým výsledkům:

- Klíč byl nalezen, strom tedy dotyčnou hodnotu již obsahuje a není třeba ji vkládat (komplikovanější varianty připouštějící vícenásobný výskyt stejného klíče by pokračovaly dál do podstromu připouštějícího rovnost).
- Algoritmus narazil na neexistující uzel, nový uzel bude vložen na toto místo, protože sem podle hodnoty svého klíče patří.

_Odstranění uzlu_

Zde nastává několik případů ke zvážení.

- _Odstranění listu_: Odstranění uzlu bez potomků se jednoduše provede odstraněním uzlu ze stromu.
- _Odstranění uzlu s jedním potomkem_: Provede se nahrazením uzlu uzlem potomka.
- _Odstranění uzlu se dvěma potomky_: Nechť se odstraněný uzel nazývá N. Pak je hodnota uzlu N nahrazena nejbližší vyšší (nejlevější uzel pravého podstromu), nebo nižší hodnotou (nejpravější uzel levého podstromu). Takový uzel má nanejvýš jednoho potomka, lze jej tedy ze stromu vyjmout podle jednoho z předchozích pravidel.

_Procházení_

Průchod binárním vyhledávacím stromem nijak nevyužívá jeho speciální vlastnosti a odpovídá průchodu běžným stromem. 

### Hashování
![[Hashovaní]]

## Prohledávání řetězců
Hledaní vzoru/patternu uvnitř textu. Dnes textové editory, vyhledávání na webu, zpracování obrazu, strukturní rozpoznávání. 

Základní pojmy:
- **Řetězec** S o velikosti m
- **Podřetězec** S\[i:j] je část řetězce S mezi indexy i a j
- **Prefix** (předpona) S je podřetězec S\[0:i]
- **Suffix** (přípona) S je podřetězec S\[i:m-1], kde i je libovolný index mezi 0 a m-1
Každé slovo je prefixem i sufixem sebe sama – takový prefix nazýváme nevlastní

### Přirozené prohledávání
Postupné procházení celého řetězce a pro každou pozici testujeme, zda na ní není začátek hledaného řetězce. 

Složitost: 
- nejhorší případ $O(m*n)$ , 
- běžně $O(m+n)$.

Algoritmus je rychlý pokud je abeceda textu „velká“ (A-Z, a-z, 1-9 atd)
Algoritmus je pomalý pro malou abecedu – tedy binární soubory, obrázkové soubory atd.

Pro přirozené hledání je typické opakované procházení již prohledaných částí, klíčem ke zrychlení procesu je inteligentní řízení procesu, toho dosáhneme heuristickou analýzou často prováděnou předem (preprocesing) 

## KMP (Knouth-Morris-Pratt)
Princip je stejný jako u přirozeného prohledávání. Algoritmus se nikdy nevrací ve vstupním textu – vhodné pro sekvenční zpracování rozsáhlých dat.

Řízení procesu:
- nastupuje pokud se vyskytne neshoda mezi textem a vzorem v pozici P\[j]
- jaký je největší možný posun vzoru abychom se vyhnuli opakovanému porovnávání

hledaný největší možný posun je roven délce největšího prefixu P\[0:j-1], který je sufixem P\[1:j-1]

chybová funkce:
- protože prefix i sufix hledáme ve vzoru, který známe předem, můžeme celou analýzu prefixů a sufixů provést předem
- označme k jako pozici před neshodou
- chybová funkce (failure function) F(k) je definována jako nejdelší prefix P\[0:k], který je také sufixem P\[1:K]

Složitost: $O(m+n)$

### Boyer-Moore
hledáme zrcadlově -začínáme na konci P a postupujeme zpět k začátku T. V okamžiku neshody můžeme přeskočit celé skupiny znaků, které se neshodují.

Existují tři situace ve kterých se v okamžiku neshodují.
(P\[j] != T\[i]) nachází vzor:
1. případ – pokud P obsahuje x, pak zkusíme posunout P doprava tak, aby se poslední výskyt x dostal proti x obsaženému v T\[i]
2. případ – P obsahuje x, ale posun doprava na poslední výskyt x není možný, pak posuneme P doprava o jeden znak k T\[i+1]
3. případ – pokud P neobsahuje x, posuneme P tak aby bylo P\[0] zarovnáno s T\[i+1], nejlepší případ – skok o celý vzor
 
#### Preprocesing
Stejně jako u KMP i zde určujeme posuny předem analýzou vzorů. Používáme zobrazení všech znaků použité abecedy A do množiny celých čísel. Pro libovolný znak x z A volíme Prep(x) jako největší index pro který platí P\[i] == x nebo -1 pokud žádný takový index v P neexistuje.

#### Časová složitost
BM algoritmu je v nejhorším případe: $O(mn + A)$.

Algoritmus je rychlejší pokud je abeceda(A) velká, pomalý pro malou abecedu, tedy stejně jako pro přirozené prohledávání (PP) je vhodný text, špatný pro binární vstupy. BM je rychlejší než PP v případě vyhledávání nad stejnou abecedou

### Rabin-Karp
Založen na použití [[Hashovaní|hašování]] – porovnání dvou otisků (hashů)
Vypočteme hash pro vzor P (délky m) a pro každý podřetězec řetězce délky m. Procházíme řetězcem T ale místo jednotlivých znaků porovnáváme hash každého podřetězce a vzoru, v případě shody provedeme test podřetězce a vzoru znak po znaku – ochrana proti kolizi haše.

Volba hašovací funkce:
Klíčová volba pro efektivitu celého algoritmu. Podřetězec se posouvá po znaku – části podřetězců jsou shodné. Potřebujeme funkci která umožní vypočítat hash následujícího podřetězce s využitím již vypočtených hashů.

Hashovací funkce
Zvolíme prvočíslo q – určuje velikost hašovacího prostoru. Zvolíme základ d, může být roven velikosti |A| nebo libovolnému většímu číslu, ideálně d = 2X. Čím větší q, tím menší pravděpodobnost kolize, d jako mocnina dvou umožňuje efektivní implementaci násobení

Pro efektivní výpočet využíváme Hornerovo schéma (polynom je v monotické formě).

Nenumerické znaky převádíme pomocí kódovací tabulky na čísla (ASCII, Unicode).

#### Časová náročnost
Přes stejnou složitost běží algoritmus pomaleji než KMP na stejných datech (díky režii výpočtů). 	Algoritmus lze ovšem snadno rozšířit na vyhledávání víc vzorů (slov) najednou – používá se v testování plagiátorství, detekce virů v binárních souborech.