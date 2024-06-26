#ALD
# Hashovaní
Hashování se používá pro efektivní vyhledávání.
Obecně jsou pro vyhledávání možné dva způsoby:
- první způsob je záznamy uspořádat nesekvenčně a potom je sekvenčně prohledávat
- druhý způsob je znát předem index požadovaného záznamu a tak se dostat k záznamu bez jakéhokoli vyhledávání

Sekvenční vyhledávání vyžaduje však při velkém objemu dat velké množství času a přímý přístup zase velké množství paměti. Proto vznikl kompromis mezi těmito způsoby, který je postaven na **hashovaní**. Pro hashování je velice důležitá **hashovací funkce**, která převádí vstupní data na index v poli, kde by měl být uložen požadovaný záznam.

Na tomto principu jsou postaveny různé datové typy nebo databázové indexi, které pracují na principu klíč hodnota. Například tedy **asociační tabulka**, **hashmap** nebo **hashtable**, tyto struktury mohou být indexovány libovolným datovým typem.

> [!example] Platí tedy:
>- Rychlejší než lineární nebo binární vyhledávání, $O(1)$.
>- Je potřeba celý klíč.
>- Nejsou možné intervalové dotazy.
>- Nebezpečí kolize (dva klíče ukazují na stejná data).

## Vyřešení kolizí
Při reálných implementacích se kolizím nelze vyhnout. Praktičtější než hledat perfektní hašovací funkci (0 kolizí) je s výskytem kolizí počítat a implementovat jejich vhodné řešení.

### Zřetězené hašování
Adresy v hašovací tabulce obsahují lineární seznamy. V případě kolize (stejná adresa) se prvek vloží na konec seznamu. V případě hledání sekvenčně procházíme konkrétní seznam.

### Otevřené hashování – Open Adress Hashing
Tabulka adres uložená do pole. V případě kolize prohledáváme určitou metodou další prvky pole, dokud nenajdeme prázdnou pozici.
Při vyhledávání postupujeme stejně – stejnou metodou procházíme, pokud nenajdeme volnou pozici znamená to, že prvek není indexován.

Hledání volné pozice – probing – určení, zda pozice v tabulce obsahuje klíč shodný s hledaným klíčem:
- search hit – klíč nalezen
- search miss – pozice je prázdná, klíč nenalezen
- jinak – na pozici je jiný klíč, hledej dál

#### Metody:
1. Lineární prohledávání (linear probing) 
2. Dvojí hešování (double hashing)

## Příklad
Chceme rozdělit 16 čísel do 4 košů.

Výpočet indexu koše
Poslouží nám funkce modulo.
Aby jsme rozdělili 16 čísel do 4 košů, tak potřebuje $mod_4()$.

$mod_4(1) = 1$
$mod_4(5) = 1$
$mod_4(8) = 0$
$mod_4(10) = 2$
$mod_4(15) = 3$

Čísla převedená do binární soustavy:

| číslo | binárně | index sloupce | index koše |
| ----- | ------- | ------------- | ---------- |
| 1     | 0001    | 00            | 01         |
| 5     | 0101    | 01            | 01         |
| 8     | 1000    | 10            | 00         |
| 10    | 1010    | 10            | 10         |
| 15    | 1111    | 11            | 11         |
> [!note]
> Všimněte si že můžeme rozdělit binární hodnotu našich zvolených čísel na 2 a 2 bity. Výsledek bude stejný jako počítat $mod_4$.

Výpočet rozměrů hash mapy:
$2^4 = 16$
$2^2*2^2 = 16$
- $2$ - počet bitů adresy koše
- 2 - počet bitů adresy sloupce

Hash-mapa:

| index prvku v řadku: | 0   | 1   | 2   | 3   | <- Koš |
| -------------------- | --- | --- | --- | --- | ------ |
| 0                    |     | 1   |     |     |        |
| 1                    |     | 5   |     |     |        |
| 2                    | 8   |     | 10  |     |        |
| 3                    |     |     |     | 15  |        |
