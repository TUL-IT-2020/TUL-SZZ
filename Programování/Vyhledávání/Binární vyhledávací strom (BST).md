# Binární vyhledávací strom (BST)

Datová struktura založená na binárním [[Stromy|stromu]], v němž jsou jednotlivé prvky (uzly) uspořádány tak, aby v tomto stromu bylo možné rychle vyhledávat danou hodnotu.

- Postaveno na principu binárního vyhledávání. (vyvážený BST strom má složitost vyhledávání $O(log_2(N))$
- Jedná se o binární strom, každý uzel tedy má nanejvýš dva potomky − levého a pravého.
- Každému uzlu je přiřazen určitý klíč. Podle hodnot těchto klíčů jsou uzly uspořádány.
- Levý podstrom uzlu obsahuje pouze klíče menší než je klíč tohoto uzlu.
- Pravý podstrom uzlu obsahuje pouze klíče větší než je klíč tohoto uzlu.
- Může (multimnožina) i nemusí (množina) podporovat duplicitní hodnoty. (ostrá a neostrá nerovnost, záleží na implementaci)
- Základ pro konstrukci abstraktnějších datových struktur jako jsou množiny, multimnožiny a asociativní pole.

![Binární vyhledávací strom](30_bst.png)

_Binární vyhledávací strom_

## Operace

Všechny operace na binárním stromě opakovaně porovnávají hodnoty klíčů. Může se jednat o triviální porovnání dvou čísel či řetězců, ale také o složitější podprogram, pokud úlohu klíče hraje kombinace několika datových položek uzlu. Kromě klíče uzel zpravidla nese další datové položky, které tvoří vlastní obsah datové struktury. Operacemi vzniká problém s vyvážením, proto byl tvořen samovyvažovací strom (**AVL**), který tyto problémy řeší automaticky.

### Vyhledávání

Vyhledání konkrétní hodnoty v binárním vyhledávacím stromu typicky probíhá rekurzivně. Začíná zpravidla v kořeni. V každém kroku porovná hledanou hodnotu s klíčem zkoumaného uzlu. Pokud jsou si rovny, hodnota byla nalezena. Je-li hledaná hodnota menší, pokračuje hledání v levém podstromu. Je-li větší, bude hledání pokračovat v pravém podstromu. Díky uspořádání stromu je cesta k hledané hodnotě jednoznačně určena.

### Přidání uzlu

Vložení nového uzlu začíná hledáním jeho pozice ve stromu – postupuje se stejně jako při vyhledávání, jako hledaná hodnota se použije klíč vkládaného uzlu. Tato fáze může vést ke dvěma různým výsledkům:

- Klíč byl nalezen, strom tedy dotyčnou hodnotu již obsahuje a není třeba ji vkládat (komplikovanější varianty připouštějící vícenásobný výskyt stejného klíče by pokračovaly dál do podstromu připouštějícího rovnost).
- Algoritmus narazil na neexistující uzel, nový uzel bude vložen na toto místo, protože sem podle hodnoty svého klíče patří.

### Odstranění uzlu

Zde nastává několik případů ke zvážení.

- _Odstranění listu_: Odstranění uzlu bez potomků se jednoduše provede odstraněním uzlu ze stromu.
- _Odstranění uzlu s jedním potomkem_: Provede se nahrazením uzlu uzlem potomka.
- _Odstranění uzlu se dvěma potomky_: Nechť se odstraněný uzel nazývá N. Pak je hodnota uzlu N nahrazena nejbližší vyšší (nejlevější uzel pravého podstromu), nebo nižší hodnotou (nejpravější uzel levého podstromu). Takový uzel má nanejvýš jednoho potomka, lze jej tedy ze stromu vyjmout podle jednoho z předchozích pravidel.

### Procházení

Průchod binárním vyhledávacím stromem nijak nevyužívá jeho speciální vlastnosti a odpovídá průchodu běžným stromem. 