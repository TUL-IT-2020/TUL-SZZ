# Normalizace, modelování, optimalizace

> Normalizace v relačním modelu, bezztrátová dekompozice, datové modelování (ER/ERA diagramy), funkční analýza (DFD diagramy), optimalizace databázových struktur (typy indexů a případy jejich využití).

## Normalizace v RMD
![[RMD - Normalizace]]

## Bezztrátová dekompozice
**bezztrátová dekompozice** = proces dělení původní relace na více schémat bez ztráty sémantiky 

- spojení tabulek, které vzniknou dekompozicí musí dát přesně původní tabulku (musí se zachovat závislosti)

S dekompozicí se setkáme při normalizování jednotlivých entit.

## Datové modelování (ER diagramy)
![[RMD - Modelování relačního modelu pomocí UML digramu]]

## Funkční analýza (DFD diagramy)
**DFD diagram** = diagram datových toků (data flow diagram) používaný v softwarovém inženýrství pro modelování funkcí systému.

DFD je typicky vícevrstvé. Nejvyšší vrstva zachycuje funkčnost celého analyzovaného problému. Nižší vrstvy se blíže věnují konkrétním částem problému. Počet takto vzniklých vrstev není nikde předepsán, vždy záleží na analytikovi, jakým způsobem analýzu a zpracování DFD zvolí. Obecně je nutné brát v potaz, že DFD slouží jak vývojářům k pochopení problému, tak i pro zákazníka ke specifikaci problému a jeho řešení.

Základní pojmy:
- **proces** - část systému, která mění vstupy na výstupy (symbolem je ovál či kruh),
- **tok** - znázorňuje přesun informací z jedné části systému do jiné (symbolem je šipka),
- **sklad** - slouží k uložení dat k pozdějšímu použití (symbolem jsou dvě vodorovné čáry s pojmenováním),
- **terminátor** - představuje externí entity, které komunikují se systémem a stojí vně systému (symbolem je obdélník).

Chyby, které je nutné při vytváření DFD eliminovat:
- černé díry - proces má pouze vstupy,
- samogenerující fce - proces má pouze výstupy,
- sklady, ve kterých se jen čte nebo zapisuje.

![Ukázka DFD](15_dfd.png)

## Optimalizace databázových struktur
**Index** = pomocná datová struktura, která slouží k urychlení základních operací nad záznamy

*(obvykle se automaticky vytvářejí pro klíčové a unikátní atributy)*

Typy indexů:
- **clustered index** - pokud jsou data uložena skoro stejně jako záznamy v indexu; častá reorganizace; náročné na údržbu při častém vkládání,
- **unclustered index** - záznamy nejsou tříděny podle žádného klíče; jednoduchá údržba; více indexů na jeden soubor,			
- **dense index** - index obsahuje ukazatel na každý záznam v datovém souboru; rychlé pro vyhledávání; náročné na kapacitu,
- **sparse index** - index obsahuje ukazatel pouze na přibližné místo v datovém souboru, kde by se měl záznam nacházet; pokud jej nenalezne musí prohledávat sekvenčně,
- **primární index** - je vytvořen na atributech které obsahují primární klíč,
- **sekundární index** - index, který není primárním indexem.

### Stromové indexy
**ISAM** 
- statická struktura
- počet diskových operací je roven hloubce stromu
- problém přetékání při vkládání nových záznamů

**B+**
- dynamická struktura
- odstraňuje problém s přetékáním (u ISAM) 
- operace vložení a mazání jsou vážené
- minimální obsazenost 50% pro každý uzel mimo root
- vyhledávání je sekvenční projití od kořene k listu
- operace na B+ stromech je nutné udržovat podle pravidel dále...

**Vložení dat do B+ stromu**

1. najít požadovaný list „L“
2. vložit data do L - pokud je volný tak pouze zapsat; v opačném případě rozdělit L na nový uzel L a L2, provést redistribuci záznamů, vložit index ukazující z L2 na otce L

Tento postup se může rekurzivně propagovat do celé větve stromu. Tímto strom roste.

**Mazání dat z B+ stromu**

1. najít požadovaný list „L“
2. odstranit záznam	- pokud je L nejméně z poloviny plný tak smazat; pokud má L pouze (d-1) záznamů provést redistribuci, půjčit si záznamy od sousedních uzlů; jinak spojit L a souseda	

V případě spojování L a souseda je třeba smazat i záznamy ukazující	na tyto dva uzly. Spojování lze propagovat až do root a tím snížit hloubku stromu.

### Hash indexy            
Principem je využití hash funkce pro mapování hledané hodnoty do místa, kde se bude nacházet (tedy například stránky na disku, či skupinu záznamů)

Typy Hash indexů:
- static hashing - stejné problémy jako ISAM
- extendible hashing - pro dynamické DB
- linear hashing - sofistikovanější metody pro indexování

#### Static hashing
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
  	
#### Extendible hashing
Hledáme řešení pro problém s přetékajícími koši. U statického se to muselo přeorganizovat, pokud jsme nechtěli mít overflow buckets. K přeorganizování je třeba celý soubor načíst a pak ho znovu zapsat, což je drahé a časově/paměťově náročné. Řešením je použití adresáře ukazatelů na koše. Pro zdvojnásobení počtu košů stačí pracovat s adresářem ukazatelů.

**Vkládání**
Stejným způsobem najdeme v adresáři ukazatel na koš kam	máme vložit. Pokud je v koši místo přidáme. Pokud ne, pak to musíme řešit. Vytvoříme nový koš,  rozdělíme data do dvou košů a zdvojnásobíme adresář s ukazateli.

**Globální hloubka** 
Určuje počet bitů, které se použijí k adresování v rámci adresáře (počet bitů na konci hash hodnoty).

**Lokální hloubka**  
Pokud budeme vkládat tak, že se budou dále vytvářet nové koše, může se stát, že bude třeba opět zdvojnásobit adresář.

#### Linear hashing
Dynamický hash, navržený pro operace vložení a mazání. Máme zde více hash funkcí h0 , h1 , h2 , ... Rozsah funkce je vždy dvakrát větší než
byl u jejího předchůdce (tedy h1 má dvakrát větší rozsah než h0). Pokud h0 adresovalo do M košů, pak h1 do 2M košů. 

### Bitmapové indexy
- vhodné pro atributy s malou kardinalitou 
- jako ideální poměr se ukazuje být 1%
- vhodné pro statické tabulky 
- díky malé kardinalitě vhodné pro dotazy s více podmínkami ve WHERE klauzuli
- uloženy jako bity -> každá hodnota v tabulce je jeden bit (true/false)
 
|    datum   |           místo výskytu          | id_druhu | část_dne | BI AM | BI PM |
|------------|----------------------------------|----------|----------|-------|-------|
| 23.2.2007  | povodí Berounky – oblast Alkazar | 300812   | AM       | 1     | 0     |
| 14.1.1999  | Lidečko – Pulčínské skály        | 3403412  | PM       | 0     | 1     |
| 31.11.2009 | Rejvíz – malé mechové jezírko    | 130045   | AM       | 1     | 0     |
| 1.11.2008  | Niagarské vodopády               | 8459712  | PM       | 0     | 1     |
| 11.4.2004  | Ostrava – Pod Sýkorovým mostem   | 7239710  | PM       | 0     | 1     |
*Tabulka 11: Příklad Bitmap indexu*
