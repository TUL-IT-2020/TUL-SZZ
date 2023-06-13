# Předávání parametrů
V programování existují různé způsoby předávání parametrů funkcím. Zde je přehled několika běžných metod:

1. Předání hodnotou (**pass by value**):
Předání hodnotou je nejjednodušší způsob předávání parametrů funkcím. Při použití tohoto způsobu se hodnota parametru zkopíruje do nové proměnné, která je přístupná uvnitř funkce. Změny provedené uvnitř funkce nemají vliv na původní hodnotu v předávané proměnné mimo funkci.

2. Předání odkazem (**pass by reference**):
Předání odkazem je mechanismus, který umožňuje funkci pracovat přímo s původní proměnnou. Namísto kopírování hodnoty se do funkce předá odkaz na původní proměnnou. Změny provedené uvnitř funkce ovlivňují původní proměnnou mimo funkci.

3. Předání ukazatelem (**pass by pointer**):
Předání ukazatelem je podobné předání odkazem. Místo předání odkazu se používá ukazatel na původní proměnnou. Ukazatel ukazuje na paměťovou adresu proměnné a umožňuje funkci přistupovat a měnit hodnotu přímo ve vyhrazené paměti.

4. Předání hodnotou a návrat hodnoty:
Někdy je vhodné použít kombinaci předání hodnotou a návratu hodnoty. To znamená, že funkce bere hodnoty jako parametry a vrací novou hodnotu jako výsledek. Tímto způsobem se zajišťuje, že původní hodnoty nejsou ovlivněny změnami uvnitř funkce.

5. Předání parametrů jako pole nebo strukturu:
Pokud je potřeba předat více parametrů najednou, lze je seskupit do pole nebo struktury a tuto strukturu pak předat funkcím. Tím se snižuje počet jednotlivých parametrů a usnadňuje se předávání dat.

Je důležité si vybrat správný způsob předávání parametrů v závislosti na potřebách a vlastnostech programu. Každá metoda má své výhody a omezení, které je třeba zvážit při návrhu a implementaci kódu.