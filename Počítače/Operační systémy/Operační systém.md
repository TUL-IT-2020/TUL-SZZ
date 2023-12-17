# Operační systém
> Operační systém, vysvětlení pojmu, typy, poskytované funkce. Správa procesů v operačním systému, vztah programu a procesu, životní cyklus procesu.

## Vysvětlení pojmu
Operační systém je v informatice základní programové vybavení počítače, které je zavedeno do paměti počítače při jeho startu a zůstává v činnosti až do jeho vypnutí. Skládá se z jádra (kernel) a pomocných systémových nástrojů. Hlavním úkolem operačního systému je zajistit uživateli možnost ovládat počítač, vytvořit pro procesy stabilní aplikační rozhraní (API) a přidělovat jim systémové zdroje. Operační systém je velmi komplexní software, jehož vývoj je mnohem složitější a náročnější, než vývoj obyčejných programů.

## Typy operačních systémů
Nejpoužívanějším druhem je OS určený pro pracovní stanice, druhou významnou skupinou 
je skupina serverových OS. Máme ovšem i speciální OS určené třeba pro velmi výkonné 
počítače anebo pro ruční počítače.

### OS pro počítače:

#### UNIX 
Je používán na strojích různého výpočetního výkonu od mikroprocesorů po střediskové počítače, a na počítačích architektur různých výrobců. Jedná se o nejstarší OS, který je dnes běžně používán. Nabízí prostředky umožňující budování komplexních programů z jednodušších. Používá hierachický systém souborů, který dovoluje jednoduchou údržbu a efektivní implementaci. Je víceuživatelský (multiuser) systém; každý uživatel může vykonávat více procesů současně (multitasking). Ukrývá před uživatelem architekturu počítače, takže zjednodušuje psaní programů provozovaných na různých implementacích technických prostředků. UNIX má několik variant. Liší se od sebe především výrobcem (komerční větev, univerzitní větev) a určením, kde a k jakým účelům má být použit (Linux je verze pro počítače typu PC). V současnosti je UNIX především využíván jako Internetový server (asi 40% celého Internetu).

#### MS-DOS 
Je operační systém firmy Microsoft, je to první operační systém určený pro jednoduchou obsluhu a byl klíčový pro obecné rozšíření PC.

#### Windows 95 
Prý plně 32–bitový OS podporující preemptivní multitasking (žádný aplikační program nemůže ohrozit běh OS, jelikož OS přiděluje veškeré výpočetní prostředky). Základem ovládání OS je práce s myší, příjemné pro uživatele aplikačního softwaru, ale zcela nevyhovující pro výkon správy počítače.

#### Windows 98 
Nástupce systému Windows 95. Neobsahuje žádné podstatné vylepšení, pouze radikálně mění uživatelské rozhraní, kde pracovní plochou je Internet Explorer. Pevné začlenění Internet Exploreru do nového OS vyústilo k soudní žalobě na firmu Microsoft. I přes to, že při prezentaci nového OS došlo k těžké havárii systému, přímo pod rukama Bila Gatese, mělo uvedení na trh v polovině roku 1998 velký komerční úspěch. Nejspíše se Windows 98 stanou na přelomu tisíciletí dominantním operačním systémem ve světě.

#### Windows NT 
Operační systém Windows NT verze 4 je dodáván buď ve verzi workstation (pro procovní stanici) nebo ve verzi server. Uživatelské rozhraní je velmi podobné jako má systém Windows 95. Ovšem vzhledem ke svým UNIXovým základům je systém daleko bezpečnější a spolehlivější (z této řady vychází i Windows XP, Vista, 7).

#### Macintosh OS 
Firma Apple pro svoje počítače dodává svůj vlastní operační systém, který uživateli připomíná vzhledm i chováním systém OS/2. Základem práce je nestarat se o to, jaký hardware je připojen, jak ho nastavit, ale vzít do ruky myš a pracovat.

#### Novell 
Firma Novell v současnosti produkuje řadu pěti síťových operačních systémů. 
Jedná se o, na DOSu založeném systému peer-to-peer, Personal NetWare:
● maximální počet 1000 uzlů na jeden server
● podpora globálních zdrojů, globálního pojmenování
● podpora komprese souborů na disku
● lepší prostředky bezpečnosti včetně auditingu síťových aktivit
● rozšířené možnosti síťové správy
● podpora odložení částí souborového systému (HCSS) na vysokokapacitních médiích
● podpora migrace dat při přechodu z nižších verzí NetWare

### OS pro mobilní systémy:
● Symbian OS - nejrozšířenější OS pro mobilní telefony, především Nokia.
● Rim BlackBerry OS - OS mobilních zařízení Blackberry.
● iPhone OS - systém mobilních telefonů iPhone a přehrávačů iPod Touch, založený na Mac OS X firmy Apple.
● Windows Mobile - OS firmy Microsoft
● Android - vyvinutý firmou Google, založený na Linuxu, nyní spravovaný Open Handset Alliance.
● Linux - platformy založené na Linuxovském jádře.
● Palm webOS - OS firmy Palm Inc.
● bada - operační systém pro mobilní telefony firmy Samsung.
● Maemo - platforma firmy Nokia založená na operačním systému Debian.

### OS pro servery: 
Wndows NT, Server 2003, Server 2008. Server 2011, UNIX (BSD, LINUX), např. distribuce: UBUNTU, FreeBSD, OpenBSD, Mandriva, atd.

● **jednouživatelské jednoúlohové** (single-user single-task) např. CP/M, MS-DOS; s podporou operačního systému běží pouze jedna aplikace.
● **jednouživatelské víceúlohové** (single-user multi-task) např. Windows 95, Windows 98; jeden uživatel může mít současně spuštěno více aplikací.
● **víceuživatelské víceúlohové** (multi-user multi-task) např. UNIX, Linux; umožňují zpracovávat požadavky více uživatelů současně systémy s reálným časem (real time) – zejména pro řízení technologických proces.

## Typy jádra
Operační systém se skládá z jádra a pomocných systémových nástrojů. Jádro je zavedeno do operační paměti při startu (bootování) počítače a je mu předáno řízení. U pokročilých operačních systémů jádro nikdy neztrácí kontrolu nad počítačem a po celou dobu jeho běhu koordinuje činnost ostatních běžících procesů. Označení kernel pochází z angličtiny, kde označuje jádro pecky, zrno nebo ztvrdlou dužinu ovoce. Hlavní úkol jádra spočívá v přidělovaní **paměti** a **času procesoru** (či procesorů) programům, ovládání zařízení počítače (pomocí ovladačů) a abstrakci funkcí (aby bylo např. možné načítat soubory z pevného disku a z jednotky CD-ROM stejným příkazem).

Pro zajištění bezpečnosti operačního systému je nutné, aby procesor podporoval dva módy činnosti: omezený pro aplikace a privilegovaný (se speciálními strojovými instrukcemi) pro jádro. Privilegovanému módu se proto někdy říká kernel mód.

Typy jader OS:
● **monolitické jádro** – jádro je jedním funkčním celkem (Linux)
● **mikrojádro** – jádro je velmi malé a všechny oddělitelné části pracují samostatně jako běžné procesy
● **hybridní jádro** – kombinuje vlastnosti monolitického jádra i mikrojádra ([[Windows|Windows]])

## Poskytované funkce operačním systémem
Operační systém plní tři základní funkce:
1. **ovládání počítače** – umožňuje uživateli spouštět programy, předávat jim vstupy a získávat jejich výstupy s výsledky,
2. **abstrakce hardware** – vytváří rozhraní pro programy, které abstrahuje ovládání hardware a dalších funkcí do snadno použitelných funkcí (API),
3. **správa prostředků** – přiděluje a odebírá procesům systémové prostředky počítače.

### Ovládání počítače 
Při definici operačního systému se obvykle omezuje ovládání počítače na schopnost spustit program, předat mu vstupní data a umožnit výstup výsledků na výstupní zařízení. Někdy je však pojem operační systém rozšířen i na grafické uživatelské rozhraní, což může být z důvodů marketingových, ale i problému nejasné hranice mezi operačním systémem a aplikacemi.
U systémů, které disponují jediným grafickým rozhraním (Microsoft Windows, Symbian OS, …) je často grafické rozhraní zahrnováno do operačního systému. U systémů, kde je uživatelské rozhraní možné vytvořit několika nezávislými způsoby nebo různými aplikacemi, je běžné nepovažovat ho za součást systému (Linux, Android).

### Abstrakce hardware 
Operační systém skrývá detaily ovládání jednotlivých zařízení v počítači (tzv. hardware) a definuje standardní rozhraní pro volání systémových služeb tak, že vytváří abstraktní vrstvu s jednoduchými funkcemi (tzv. API), které využívají programátoři aplikací. Tím nejen zjednodušuje programátorům vytváření programů, ale umožňuje programům pracovat i se zařízeními, které v době vzniku programu neexistovaly (například z hlediska programátora není rozdíl mezi otevřením souboru na 
pevném disku, CD, DVD, flash, síťovém disku nebo Blu-ray). Někdy je uvnitř operačního systému vytvářena podobná abstraktní mezivrstva, která usnadňuje programování ovladačů jednotlivých zařízení.

### Správa zdrojů 
Operační systém přiděluje spuštěným programům systémové prostředky (operační paměť, procesor, pevný disk, vstupně-výstupní zařízení). V případě potřeby může operační systém procesům přidělené prostředky násilně odebrat (preempce). 
Operační systém využívá schopnosti procesoru k ochraně sebe samého, ale i k oddělení pracovního prostoru jednotlivých procesů.

## Správa procesů
Moderní operační systémy umožňují spustit zároveň více procesů což nazýváme multitasking. Pokud je v počítači méně procesorů, než je běžících procesů, musejí se procesy na procesorech střídat, což označujeme jako změnu kontextu. Změna kontextu je operace, při níž multitaskingový operační systém přepíná řízení mezi procesy. Při tom se ukládá a načítá aktuální stav procesoru. Tento děj se u moderních procesorů opakuje mnohokrát za sekundu. Změny kontextu jsou obvykle výpočetně intenzivní a hodně plánované a operační systémy jsou k tomu optimalizované. Změnou kontextu můžeme myslet změnu kontextu registrů, vláken, úloh a procesů. Ke které změně kontextu dojde, záleží na procesoru nebo operačním systému.

### Nepreemptivní (kooperativní) multitasking
Nepreemptivní multitasking vyžaduje aktivní spoluúčast běžících úloh. Každá úloha je povinna dostatečně často systémovým voláním předat řízení zpět operačnímu systému, který díky tomu může spustit jinou úlohu, která se po chvíli opět **dobrovolně vzdá** procesoru atd. Výhodou řešení je jednodušší implementace operačního systému. 
Podstatnou nevýhodou je skutečnost, že chybně naprogramovaná úloha, která nevrátí řízení zpět operačnímu systému, způsobí úplné zastavení systému i ostatních úloh (Windows 95, 98).

### Preemptivní multitasking
V preemptivním multitaskingu o přidělování a odebírání procesoru jednotlivým úlohám plně rozhoduje operační systém. V pravidelných intervalech (typicky zhruba 100× až 1000× za sekundu) přeruší provádění běžícího programu, vyhodnotí aktuální situaci (které úlohy žádají o přidělení procesoru, jejich priority atd.) a nechá běžet buď opět úlohu, kterou přerušil, nebo jinou úlohu, která má zájem o přidělení procesoru. I v preemptivním multitaskingu však může úloha dobrovolně požádat o přepnutí kontextu a vzdát se zbytku svého kvanta (úloha takzvaně „usne“ nebo se zablokuje provedením pomalé vstupně-výstupní operace, jako je například čtení dat z pevného disku). Výhodou tohoto řešení je, že nedochází k „zatuhnutí“ počítače, neboť i v případě, 
že se úloha zacyklí, odebere operační systém pomocí časovače dané úloze řízení a přidělí procesor jiné úloze. Nevýhodou je složitější implementace operačního systému a nutnost hardwarové podpory v procesoru počítače (viz privilegovaný režim) (Windows NT, unixové systémy).

## Program, proces
Počítačový program je v informatice postup operací, který popisuje realizaci dané úlohy. Počítačový program může být vytvořen programátorem zápisem algoritmu v nějakém programovacím jazyce. Zapsaný program může být v počítači prováděn interpretem nebo může být pomocí překladače nejprve přeložen do strojového kódu a teprve pak přímo prováděn mikroprocesorem.

Proces je v informatice název pro spuštěný počítačový program. Proces je umístěn v operační paměti počítače v podobě sledu strojových instrukcí vykonávaných procesorem. Obsahuje nejen kód vykonávaného programu, ale i dynamicky měnící se data, která proces zpracovává. Jeden program může v počítači běžet jako více procesů s různými daty (například vícekrát spuštěný webový prohlížeč zobrazující různé stránky). Správu procesů vykonává operační systém, který zajišťuje jejich oddělený běh, přiděluje jim systémové prostředky počítače a umožňuje uživateli procesy spravovat.

### Životní cyklus procesu
Životní cyklus procesu probíhá podle diagramu stavových přechodů. U několika soupeřících procesů je zařazení k běhu řízeno pravidly: časová kvanta, priorita, či bez možnosti přerušení. Přepínání procesů je značně časově náročné a může vyhovovat jen pro toleranci událostí s dlouhou latencí.

Proces je vytvořen buď příkazem uživatele (u terminálu), nebo na žádost operačního systému o provedení služby, či na žádost jiného procesu (rodiče). 

- **připravený**
„vytvořený“ proces je ve stavu „připravený“ – připravený k vykonání a čeká pouze na přidělení procesoru. spuštěním procesu, na základě plánovacího algoritmu přechází proces do stavu „běžící“

- **běžící**
„běžící“ proces může být ukončen normálně, tj. byl celý proveden, nebo násilně ukončen uživatelem, provedením chybné strojové instrukce, chybou vstupně–výstupní zařízení, porušením ochrany paměti, nebo na žádost rodiče apod. „běžící“ proces může být po vypršením časového limitu pro jeho běh (uplynutí maximální časového kvanta) převeden do stavu „připravený“. „běžící“ proces může být jen jeden, máme-li jen jeden procesor, kdežto ve stavu „připravený“ může být více procesů zařazených do fronty nebo jiné datové struktury, kterou využívá plánovací algoritmus

![[spuštění.PNG]]

#### Základní stavy procesů: 
Následující stavy procesů se vyskytují ve všech víceúlohových systémech:
- vytvořený (**created**) – proces je vytvořen buď příkazem uživatele (u terminálu), nebo na žádost operačního systému o provedení služby, či na žádost jiného procesu (rodiče)
- připravený (**ready**) nebo čekající (**waiting**) – připravený pro vstup do stavu běžící, čeká pouze na přidělení procesoru
- běžící (**running**) – procesu je přidělen procesor a právě se provádí příslušné programy
- blokovaný (**blocked**) – proces je převeden do tohoto stavu v případě, kdy čeká na dokončení nějaké vstupně–výstupní operace, případně na skončení jiného procesu, uvolnění zdroje, synchronizační primitivum a podobně
- ukončený (**terminated**) – proces skončil

![[životní proces s vyrtuální pamětí.PNG]]

![[Životní cyklus procesu.PNG]]
