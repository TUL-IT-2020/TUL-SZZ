# Ethernet
Ethernet je název souhrnu technologií pro počítačové sítě (LAN, MAN) z větší části standardizovaných jako IEEE 802.3, které používají kabely s kroucenou dvoulinkou, optické kabely (ve starší verzích i koaxiální kabely) pro komunikaci přenosovými rychlostmi od 10 Mbit/s po 100 Gbit/s. Sítě Ethernet realizují fyzickou a linkovou vrstvu referenčního modelu OSI, takže je možné po nich provozovat jeden nebo více protokolů síťové vrstvy, například AppleTalk, DECnet, IPX/SPX, a především protokoly IPv4 a IPv6, které se používají pro služby sítě Internet.

Ještě před rokem 2000 se Ethernet stal dominantní technologií pro drátové nebo kabelové lokální sítě a prakticky synonymem pro lokální síť (LAN). Používá se nejen pro propojování počítačů, ale i pro datová úložiště, zařízení spotřební elektroniky jako jsou televizní přijímače a herní konzole a také jako drátové rozhraní pro přístupové body WiFi a zařízení pro přístup k Internetu. Pokud zařízení deklaruje, že má připojení na LAN, v naprosté většině případů to znamená, že je vybaveno konektorem 8P8C (RJ-45) pro síť Ethernet s rychlostí 100 nebo 1000 Mbit/s.

Všechna zařízení splňující standardy IEEE 802.3 vyrobená po roce 1985 lze propojit do jedné sítě díky stejnému základnímu formátu rámce a MAC adres. Přitom však zařízení, která používají různé přenosové médium nebo nejsou schopna pracovat stejnou přenosovou rychlostí, nelze propojovat přímo, ale musí být připojena do různých segmentů sítě. Jednotlivé segmenty se propojují pomocí několika druhů aktivních prvků.

## Vývoj
### Experimentální Ethernet 
Ethernet byl vyvinut v letech 1972–1975 v laboratořích PARC firmy Xerox. Název vychází ze slova éter, což měla být látka, která má umožňovat šíření elektromagnetického záření. První verze Ethernetu používaly pro šíření signálu koaxiální kabel, ke kterému mohlo být připojeno až několik desítek počítačů. Pořádek v síti, ve které kvůli použití signálu v základním pásmu s linkovým kódem Manchester může v každém okamžiku vysílat nejvýše jeden počítač, zajišťuje souhrn pravidel pro přístup k médiu nazývaným CSMA/CD. Experimentální verze sítě Ethernet pracovala s přenosovou rychlostí 2,94 Mbit/s.

### Ethernet I
V roce 1980 byla představena první komerční verze Ethernetu s přenosovou rychlostí 10 Mbit/s vyvinutá firmami DEC, Intel a Xerox (z jejich jmen vznikla zkratka DIX-Ethernet) určená k propojení počítačů pro potřeby kancelářských aplikací. Tato varianta označovaná Ethernet I se v základních rysech shodovala s 10BASE5 a v roce 1982 byla standardizována také sdružením evropských výrobců počítačů ECMA (European Computer Manufacturers Association), ale od roku 1985 se již nepoužívá.

### IEEE 802.3
V roce 1983 byla poněkud upravená verze normalizována institutem IEEE jako IEEE 802.3. Později byla převzata také Mezinárodní organizací pro normalizaci jako ISO 8802-3; institut IEEE poté převzal iniciativu a naprostá většina dalších rozšíření vznikla pod jeho hlavičkou. Standardy IEEE se dlouhou dobu názvu Ethernet vyhýbaly a nesly název „IEEE 802.3 Carrier Sense Multiple Access with Collision Detection ([[CSMA-CD|CSMA/CD]]) Access Method and Physical Layer Specifications“, protože Ethernet byla registrovaná značka firmy Xerox. IEEE standard z roku 2012 však již nese název „IEEE Standard for Ethernet“.

### Ethernet II
Po vytvoření standardu IEEE 802.3 byl DIX-Ethernet v některých detailech upraven s cílem dosáhnout lepší kompatibility se standardem IEEE, čímž vznikl Ethernet II (označovaný za průmyslový standard). Prvky vyráběné po roce 1985 vyhovují jak standardu IEEE 802.3, tak Ethernet II. Jediný větší rozdíl byl ve formátu rámce, který je řešitelný softwarově, a od přijetí standardu IEEE 802.3x v roce 1999 je používání rámců Ethernet II součástí standardu IEEE.

### Aktuální stav
V roce 2013 je naprostá většina zařízení, která lze připojit na drátovou síť jako jsou notebooky, netbooky, stolní počítače, herní konzole, některé televizní přijímače, datová úložiště, tiskárny i zařízení pro přístup k Internetu jako jsou DSL adaptéry, kabelové modemy, přístupové body používající technologii Wi-Fi nebo jiné bezdrátové technologie, vybavena konektorem 8P8C (RJ-45) pro síť Ethernet.

Nejobvyklejší rychlost ethernetových rozhraní je 100 Mbit/s; zařízení a komponenty pracující s nižší rychlostí se již neprodávají (ale je možné je připojovat díky zpětné kompatibilitě nových prvků), ale zvyšuje se podíl zařízení s rychlostí 10 Gbit/s. Pro výkonné servery jsou k dispozici komponenty s rychlostí 100 Gbit/s.

Přestože tato zařízení mohou pracovat různými přenosovými rychlostmi, je možné je spolu vzájemně propojit, protože modernější prvky jsou vždy schopné pracovat i nižšími rychlostmi, pokud protistrana vyšší rychlost nepodporuje nebo pokud použitý kabel nemá dostatečnou kvalitu.

## Rychlost přenosu 
Dlouhodobý úspěch Ethernetu by nebyl možný bez neustálého vývoje, jehož klíčovými body byl přechod od používání koaxiálního kabelu na kroucenou dvoulinku a optické kabely a neustálé zvyšování přenosové rychlosti. Komerční verze sítě Ethernet používají následující rychlosti: 
- 1 Mbit/s – tuto rychlost používaly první varianty Ethernetu pro kroucenou dvoulinku vyvinuté v roce 1984 firmou AT&T jako StarLAN a standardizované jako IEEE 802.3e v roce 1986; jejich rozšíření bylo minimální, ale otevřely cestu k používání Ethernetu po kroucené dvoulince  10 Mbit/s – klasický Ethernet – původní varianta s přenosovou rychlostí 10 Mbit/s. Definována pro koaxiální kabel, kroucenou dvojlinku a optické vlákno.
- 100 Mbit/s – Fast Ethernet – rychlejší verze s přenosovou rychlostí 100 Mbit/s definovaná standardem IEEE 802.3u. Převzala maximum prvků z původního Ethernetu (formát rámce, algoritmus CSMA/CD apod.), aby se usnadnil, urychlil a zlevnil vývoj. V současnosti ji lze považovat za základní verzi Ethernetu. Je k dispozici pro kroucenou dvojlinku a optická vlákna.
- 1 Gbit/s – Gigabit Ethernet – zvýšil přenosovou rychlost na 1 Gbit/s. Opět recykloval co nejvíce prvků z původního Ethernetu, teoreticky i algoritmus CSMA/CD. V praxi je ale gigabitový Ethernet provozován pouze přepínaně s plným duplexem. Důležité je především použití stejného formátu rámce. Původně byl definován pouze pro optická vlákna (IEEE 802.3z), později byla doplněna i varianta pro kroucenou dvojlinku (IEEE 802.3ab).
- 10 Gbit/s – 10 Gigabit Ethernet – představuje zatím poslední standardizovanou verzi. Jeho definice byla jako IEEE 802.3ae přijata v roce 2003. Přenosová rychlost činí 10 Gbit/s, jako médium zatím slouží hlavně optická vlákna a opět používá stejný formát rámce. Algoritmus CSMA/CD byl definitivně opuštěn, tato verze pracuje vždy plně duplexně. V současnosti (2008) byla vyvinuta jeho specifikace pro kroucenou dvojlinku s označení IEEE 802.3an. Začíná se zavádět.
- 40, 100, 400, 1000 Gbit/s – vyšší rychlosti se zatím (rok 2013) příliš nerozšířily nebo jsou ve vývoji; v letech 2007-2012 představila většina předních výrobců síťových komponent zařízení pro rychlosti 40 a 100 Gbit/s a v březnu 2013 byla vytvořena pracovní skupina IEEE 802.3 pro Ethernet o rychlosti 400 Gbit/s

## Ethernetový rámec
Ethernetový rámec je protokolová datová jednotka linkové vrstvy v síti Ethernet. Na fyzické vrstvě mu předchází preambule a oddělovač začátku rámce (SFD), které s ethernetovým rámcem tvoří paket.

Ethernetový rámec začíná ethernetovou hlavičkou, která obsahuje cílovou a zdrojovou MAC adresu (anglicky Destination MAC Address, Source MAC Address) a pole Délka/Typ (anglicky Length/Type). Dále obsahuje datové pole (anglicky Payload) a kontrolní posloupnost rámce (anglicky Frame Control Check, FCS), což je 32-bitový cyklický redundantní součet používaný pro detekci poškození dat při přenosu.

Datové pole v ethernetovém rámci začíná hlavičkou protokolu (například Internet Protocol) přenášeného v rámci.

- Ethernetový rámec to jediné, čemu rozumí ethernetová karta 
	- linková vrstva modelu ISO/OSI, formát podle: 
		- IEEE 802.2, IEEE 802.3, Ethernet SNAP 
		- Ethernet II – průmyslový standard, běžně používán 
	- hlavička + přepravovaná data 
		- 14 + (48 až 1500) + 4 oktety 
	- protokoly vyšších vrstev v datové části 
	- síťová karta zachytává vše 
		- pokud je určeno pro ni, vyvolá přerušení → ovladač, pozná se podle cílové MAC adresy, případně linkový broadcast, jinak ignoruje (výjimkou je promiskuitní režim).