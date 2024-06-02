# Hash indexy
Principem je využití hash funkce pro mapování hledané hodnoty do místa, kde se bude nacházet (tedy například stránky na disku, či skupinu záznamů)

> [!example] Typy Hash indexů:
>- static hashing - stejné problémy jako ISAM
>- extendible hashing - pro dynamické DB
>- linear hashing - sofistikovanější metody pro indexování

## Static hashing
Máme seznam „buckets“ (koše). Jeden primární a případně více dalších (přetékajících) košů. Soubor obsahuje n-1 košů s tím, že v každém je na počátku jedna stránka. Každý koš může obsahovat záznamy uložené jako hromada, tříděný soubor, hash soubor.

**Hash funkce** je základní prvek ovlivňující efektivitu. Musí distribuovat záznamy do košů rovnoměrně.

**Vyhledávání**  
Při hledání záznamu, nejprve aplikuje hash funkce, která identifikuje koš, ve kterém se bude daná položka nalézat.

**Vkládání**
Použijeme hash funkci, abychom identifikovali správný koš, do kterého budeme vkládat záznam. Pokud zde již není místo, musíme přidat tzv. overflow bucket.

**Mazání** 
Použijeme hash funkci pro identifikaci koše, kde budeme mazat. Pokud se jednalo o poslední záznam v overflow bucket, pak se tento označí jako prázdný.

**Overflow bucket**
Hlavním problémem je právě zmíněný pevný počet košů, které při vládání mohou začít přetékat. Případně pokud se bude hodně mazat, pak
budeme plýtvat místem. Pomocí hash funkce nelze přímo adresovat konkrétní prvky. Je nutné po výpočtu hash a identifikaci koše projít všechny ostatní.

## Extendible hashing
Hledáme řešení pro problém s přetékajícími koši. U statického se to muselo přeorganizovat, pokud jsme nechtěli mít overflow buckets. K přeorganizování je třeba celý soubor načíst a pak ho znovu zapsat, což je drahé a časově/paměťově náročné. Řešením je použití adresáře ukazatelů na koše. Pro zdvojnásobení počtu košů stačí pracovat s adresářem ukazatelů.

**Vkládání**
Stejným způsobem najdeme v adresáři ukazatel na koš kam	máme vložit. Pokud je v koši místo přidáme. Pokud ne, pak to musíme řešit. Vytvoříme nový koš,  rozdělíme data do dvou košů a zdvojnásobíme adresář s ukazateli.

**Globální hloubka** 
Určuje počet bitů, které se použijí k adresování v rámci adresáře (počet bitů na konci hash hodnoty).

**Lokální hloubka**  
Pokud budeme vkládat tak, že se budou dále vytvářet nové koše, může se stát, že bude třeba opět zdvojnásobit adresář.

## Linear hashing
Dynamický hash, navržený pro operace vložení a mazání. Máme zde více hash funkcí h0 , h1 , h2 , ... Rozsah funkce je vždy dvakrát větší než
byl u jejího předchůdce (tedy h1 má dvakrát větší rozsah než h0). Pokud h0 adresovalo do M košů, pak h1 do 2M košů. 