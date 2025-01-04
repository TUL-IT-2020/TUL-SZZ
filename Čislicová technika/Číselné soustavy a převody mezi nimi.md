## Číselné soustavy:

1. **Dvojková soustava (binární):**
    - Používá pouze dvě číslice: 0 a 1.
    - Každá pozice v čísle reprezentuje mocninu čísla 2.
2. **Osmičková soustava (oktální):**    
    - Základní soustava se 8 číslicemi: 0, 1, 2, 3, 4, 5, 6, 7.
    - Každá pozice reprezentuje mocninu čísla 8.
3. **Desítková soustava (dekadická):**    
    - Běžně používaná soustava s deseti číslicemi: 0-9.
    - Každá pozice reprezentuje mocninu čísla 10.
4. **Šestnáctková soustava (hexadecimální):**    
    - Využívá 16 číslic: 0-9 a písmena A-F, kde A = 10, B = 11, ..., F = 15.
    - Často se používá v informatice pro zkrácení zápisu binárních čísel.

### Převody mezi číselnými soustavami:

1. **Binární na desítkovou:**
    - Každá pozice v binárním čísle reprezentuje mocninu čísla 2.
    - Součet hodnot na jednotlivých pozicích dává ekvivalentní desítkovou hodnotu.
2. **Desítková na binární:**
    - Číslo je postupně děleno 2 a zbytky tvoří binární zápis, který se čte zprava doleva.
3. **Ostatní převody:**
    - Obdobné postupy lze aplikovat na převody mezi osmičkovou a šestnáctkovou soustavou.

### Kódování čísel s pevnou a pohyblivou řádovou tečkou:

1. **Pevná řádová tečka:**
    - Čísla jsou reprezentována s pevně danou pozicí desetinné tečky.
    - Například v informatice může být reprezentována fixní délka paměti pro celá a desetinná čísla.
2. **Pohyblivá řádová tečka:**
    - Umožňuje variabilitu polohy desetinné tečky.
    - Typický formát pro reprezentaci racionálních čísel s proměnnou přesností.
    - [[Float]]

### Kódování záporných čísel:

1. **Znaménková magnitude:**
    - Jeden bit je vyhrazen pro znaménko a ostatní bity pro absolutní hodnotu čísla.
    - Záporné číslo je reprezentováno invertovaním bitů absolutní hodnoty.
2. **Doplňkový kód:**
    - Pro záporné číslo se invertují bity absolutní hodnoty.
    - K invertovaným bitům se přičte 1.
    - [[Dvojkový doplněk]]
1. **Dvoukomplementární kód:**
    - Podobný doplňkovému kódu, ale záporné číslo se získá invertováním bitů a následným přičtením 1.