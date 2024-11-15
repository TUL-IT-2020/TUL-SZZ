#ALD 
# Stromy
## B strom

Druh stromu, který zavádí limity na maximální (konstantou n), i minimální (n/2) počet potomků vrcholu. B-strom je díky této vlastnosti vyvážený, operace přidání, vyjmutí i vyhledávání tedy probíhají v logaritmickém čase. Tato struktura je často používána v aplikacích, kdy není celá struktura uložena v paměti RAM, ale v nějaké sekundární paměti, jako je pevný disk (například databáze). Protože přístup do tohoto typu paměti je náročný na čas (hlavně vyhledání náhodné položky), snažíme se minimalizovat počet přístupů do této paměti.

**B+ Strom** - všechny hodnoty musí být v listech.

![B strom odebírání](30_b_strom.png)

_B strom_

- Všechny listy (tj.uzly které nemají žádné potomky) jsou na stejné úrovni (ve stejné hloubce).
- Všechny vnitřní uzly kromě kořene mají maximálně n a minimálně n/2 potomků.
- Kořen má nejvýše n potomků, spodní hranice není omezena.

Strom je vyvažován požadavkem, aby byly všechny listy na stejné úrovni. Tato hloubka pozvolna roste s tím, jak do stromu přidáváme další data, nebo klesá spolu s vymazáváním dat ze stromu.

**Operace**

_Vyhledávání_

_Přidání uzlu_

_Odstranění uzlu_

## 2-3 strom

**2-3 strom** je druh stromu, který se označuje v počítačové terminologii jako **B-strom** obsahující pouze uzly s dvěma nebo třemi potomky. Všechny listy ve stejné hloubce, proto se 2‑3 strom řadí mezi vyvážené stromy.

![2-3 strom](30_23_strom.png)

_2-3 strom_

Vnitřní uzly neobsahují uvnitř data, ale obsahují některé informace o tom, co je uloženo v jejich potomcích (podstromech).

- Všechny cesty od kořene k listům jsou stejně dlouhé.
- Data jsou zapsána v listech v poslední úrovni stromu.
- Listy jsou seřazeny podle klíče z leva (minimum) doprava (maximum).
- Jestliže vnitřní část uzlu obsahuje jeden klíč, uzel má dva potomky. Pokud vnitřní část uzlu má dva klíče, uzel má tři potomky. V případě listu uzel nemá žádné potomky.

**Operace**

2-3 stromy se využívají v datových strukturách, jako jsou seznamy nebo databáze, kde se pracuje se základními operacemi vyhledávání, vkládání a mazání prvků. Usnadňují tak daleko více práci s daty, než kdybychom měli data uspořádána libovolně v paměti (obtížné vyhledávání) nebo naopak uložená jako seznam v řadě za sebou (obtížné vkládání).

_Vyhledávání_

Při vyhledávání dat podle klíče začínáme u kořene stromu a postupujeme podle klíčových atributů shora dolů.

- Procházíme uzel se dvěma potomky:

  - Pokud hledaný klíč K je menší než klíčový atribut uzlu K1, hledáme dále v levém podstromu.
  - Jestliže hledaný klíč K je větší nebo roven K1, pak hledáme dál v pravém podstromu.

![2-3 strom 2 listy](30_23_strom_2.png)

_2-3 strom 2 listy_

- Procházíme uzel se třemi potomky:

  - Pokud hledaný klíč K je menší než klíčový atribut uzlu K1, hledáme dále v levém podstromu.
  - Jestliže je hledaný klíč K větší nebo roven K1 a zároveň pokud je ve vnitřní části uzlu klíčový atribut K2 větší než K pak hledáme v prostředním podstromu.
  - Pokud K je větší nebo rovno K2, hledáme dále v pravém podstromu.

![2-3 strom 3 listy](30_23_strom_3.png)

_2-3 strom 3 listy_

Tímto způsobem pokračujeme, až do poslední úrovně stromu, kde se nachází listy s daty.

_Přidání uzlu_

Při vkládání nové větve do 2-3 stromu je nutné vyhledat pozici, kam novou větev vložíme. Poté co je nalezena pozice, vložíme větev do příslušného rodiče r.

- Jestliže počet potomků rodiče r se rozšíří ze dvou na tři u 2-3 stromu můžeme daný prvek rovnou vložit.
- Pokud počet potomků r po vložení se zvýší ze tří na čtyři, r se rozdělí na dva uzly po dvou potomcích a tím se zvýší počet potomků předka r o jeden viz obrázek.

![2-3 strom vkládání](30_23_strom_vkladani.png)

_2-3 strom vkládání_

_Odstranění uzlu_

Nejprve je nutné vyhledat větev, kterou budeme odebírat. Poté se odebere větev z jejího rodiče r.

- Pokud se sníží počet potomků r ze tří na dva u 2-3 stromu provedou se jednoduché změny viz obrázek 11.
- Jestliže počet potomků r se sníží ze dvou na jeden

  - r se sloučí se svými dvěma sourozenci a vzniknou tak dvě větve, které si rozdělí potomky.
  - r převezme jednu větev z jednoho ze svých sourozenců, který leží vedle.
  - Pokud po odebrání r má dohromady se svým sourozencem jen tři potomky vezme si r jednu větev ze svého rodiče.

![2-3 strom odebírání](30_23_strom_odebirani.png)

_2-3 strom odebírání_