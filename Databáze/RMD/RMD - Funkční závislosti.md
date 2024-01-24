#SQL
# Funkční závislost
Funkční závislost je v databázi vztah mezi atributy takový, že máme-li **atribut Y je funkčně závislý na atributu X píšeme X → Y**, pak se nemůže stát aby dva řádky mající stejnou hodnotu atributu X měly různou hodnotu Y.

Pomocí funkčních závislostí můžeme automaticky navrhnout schéma databáze a předejít problémům jako je **redundance**, **nekonzistence** databáze, zablokování při vkládání záznamů, apod.

Postup datové analýzy s automatickým navržením struktury databáze je následující:
- ze zadání zjistím, co je třeba v databázi evidovat (objekty, atributy, vztahy, integritní omezení,...)
- funkční analýzou určím závislosti (vztahy) mezi atributy
- vytvořím jednu obrovskou tabulku (relaci), obsahující všechny atributy
- pomocí funkčních závislostí provedu dekompozici (rozbití) velké relace na menší, které vytvoří výsledné schéma databáze.

Příklad:
Atribut 'datum narození' je **funkčně závislý** na atributu 'rodné číslo'.
Nemůže se stát, že u záznamů se stejnými rodnými čísly bude různé datum narození.

## Armstrongovy axiomy
Armstrongovy axiomy jsou odvozovací pravidla funkčních závislostí. Pomocí axiomu získáme uzávěr funkčních závislostí spolu s klíči schemat.
**Uzávěr X+** je množina všech atributů funkčně závislá na atributech množiny X. [![](http://lucie.zolta.cz/images/ikona-zdroje-12.jpg)](http://barborka.vsb.cz/prednasky/presentations/2006-TZD-Teorie_zpracovani_dat-slides/07/tzd7_pdf.pdf "Celá definice z TZD (slajd 14)")

Armstrongový axiomy - A = množina všech atributů, F = množina všech funkčních závislostí, XY = X∪Y (X nebo Y):

- **Triviální**
  Triviální FZ DE → E  
- **Reflexivita** - je-li Y ⊂ X ⊂ A, pak X → Y
- **Tranzitivita** - pokud je X → Y a Y → Z, pak X → Z
  Tranzitívnost A → G, G → H ⇒ A → H
- **Pseudotranzitivita** -  pokud je X → Y a WY → Z, pak XW → Z
- **Sjednocení** - pokud je X → Y a X → Z, pak X  → YZ
  Spojení pravé strany (union, combination) A → BC, A → G ⇒ A → BCG
- **Dekompozice** - pokud je X → YZ, pak  X  → Y a X → Z
  Rozdělení pravé strany (decomposition, splitting) A → BC ⇒ A → B, A → C
- **Rozšíření** - pokud je X → Y a  Z ⊂ A, pak  XZ  → YZ
  Rozšíření (augmentation) A → G ⇒ AD → GD
- **Zúžení** - pokud je X → Y a  Z  ⊂  Y, pak  X → Z

## Zdroje:
- http://lucie.zolta.cz/index.php/iformacni-systemy-databaze/47-funkcni-zavislosti