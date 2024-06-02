# Typy indexů:
- **clustered index** - pokud jsou data uložena skoro stejně jako záznamy v indexu; častá reorganizace; náročné na údržbu při častém vkládání,
- **unclustered index** - záznamy nejsou tříděny podle žádného klíče; jednoduchá údržba; více indexů na jeden soubor,			
- **dense index** - index obsahuje ukazatel na každý záznam v datovém souboru; rychlé pro vyhledávání; náročné na kapacitu,
- **sparse index** - index obsahuje ukazatel pouze na přibližné místo v datovém souboru, kde by se měl záznam nacházet; pokud jej nenalezne musí prohledávat sekvenčně,
- **primární index** - je vytvořen na atributech které obsahují primární klíč,
- **sekundární index** - index, který není primárním indexem.