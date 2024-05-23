# Počítačové sítě
> [!abstract] 
> Principy vrstvené architektury počítačových sítí, referenční model OSI. Charakteristika lokálních počítačových sítí. Technologie Ethernet, její principy a vývoj, algoritmus CSMA/CD. Bezdrátové lokální sítě standardu IEEE 802.11.

## Referenční model OSI 
Referenční model ISO/OSI vypracovala organizace ISO jako hlavní část snahy o standardizaci počítačových sítí nazvané OSI a v roce 1984 ho přijala jako mezinárodní normu ISO 7498. Kompletní text normy přijala také CCITT jako doporučení X.200. Referenční model ISO/OSI se používá jako názorný příklad řešení komunikace v počítačových a telekomunikačních sítích pomocí vrstevnatého modelu, kde jsou jednotlivé vrstvy nezávislé a snadno nenahraditelné. 

Úlohou referenčního modelu je poskytnout základnu pro vypracování norem pro účely propojování systémů. Otevřený systém podle tohoto modelu je abstraktním modelem reálného otevřeného systému. Norma tedy nespecifikuje implementaci (realizaci) systémů, ale uvádí všeobecné principy sedmivrstvé síťové architektury. Popisuje vrstvy, jejich funkce a služby. Nejsou zde zařazeny žádné protokoly, které by vyžadovaly zbytečně mnoho detailů. 

V praxi je model využit pro programování jednotlivých součástí síťového subsystému v modulech, které reprezentují jednotlivé vrstvy a komunikují mezi sebou pomocí rozhraní (API). Díky tomu je možné jednotlivé části snadněji naprogramovat a nezávisle nahrazovat (například vyměnit síťovou kartu, ovladač, aplikaci a zároveň ponechat ostatní součásti beze změny). Reálně je vrstevný model použit například u rodiny protokolů TCP/IP, kde jsou však použity jen čtyři vrstvy.

Rozložení řešení síťové problematiky:
- vznikne několik vrstev 
	- každá vrstva řeší dílčí problém síťové komunikace 
	- vrstvy lze snadno nahradit (zaměnit) 
		- např. vyměnit síťovku, ovladač a vše ostatní může zůstat 
		- (tj. knihovní funkce pro TCCP/IP i aplikace) 
		- SSL je jen další vsunutá mezivrstva bez vlivu na TCP i aplikaci 
- vrstvy podle ISO/OSI – „úřední“ nařízení, složité, neujalo se 
- vrstvy podle TCP/IP – jednodušší, existuje funkční implementace

![[OSI vs TCP-IP.PNG]]

### Fyzická vrstva 
Vrstva č. 1, anglicky physical layer. Specifikuje fyzickou komunikaci. Aktivuje, udržuje a deaktivuje fyzické spoje (např. komutovaný spoj) mezi koncovými systémy. Fyzické spojení může být dvoubodové (sériová linka) nebo mnohobodové (Ethernet). 

Fyzická vrstva definuje všechny elektrické a fyzikální vlastnosti zařízení. Obsahuje rozložení pinů, napěťové úrovně a specifikuje vlastnosti kabelů; stanovuje způsob přenosu "jedniček a nul". Huby, opakovače, síťové adaptéry a hostitelské adaptéry (Host Bus Adapters používané v síťových úložištích SAN) jsou právě zařízení pracující na této vrstvě. 

Hlavní funkce poskytované fyzickou vrstvou jsou:
- Navazování a ukončování spojení s komunikačním médiem.
- Spolupráce na efektivním rozložení všech zdrojů mezi všechny uživatele.
-  Modulace neboli konverze digitálních dat na signály používané přenosovým médiem (a zpět) (A/D, D/A převodníky).

### Síťová vrstva
Vrstva č. 3, anglicky network layer. Tato vrstva se stará o směrování v síti a síťové adresování. Poskytuje spojení mezi systémy, které spolu přímo nesousedí. Obsahuje funkce, které umožňují překlenout rozdílné vlastnosti technologií v přenosových sítích.

Síťová vrstva poskytuje funkce k zajištění přenosu dat různé délky od zdroje k příjemci skrze jednu 
případně několik vzájemně propojených sítí při zachování kvality služby, kterou požaduje přenosová vrstva. Síťová vrstva poskytuje směrovací funkce a také reportuje o problémech při doručování dat. Veškeré směrovače pracují na této vrstvě a posílají data do jiných sítí. Zde se již pracuje s hierarchickou strukturou adres. Nejznámější protokol pracující na 3. vrstvě je Internetový Protokol ([[Protokol IP (Internet Protocol)|IP]]). Jednotkou informace je paket.

### Transportní vrstva
Vrstva č. 4, anglicky transport layer. Tato vrstva zajišťuje přenos dat mezi koncovými uzly. Jejím účelem je poskytnout takovou kvalitu přenosu, jakou požadují vyšší vrstvy. Vrstva nabízí spojově (TCP) a nespojově orientované (UDP) protokoly.
- (TCP a UDP platí pouze pro architekturu TCP\IP)
- TCP – Zajišťuje přenos dat se zárukami, který vyžadují aplikace, kde nesmí „chybět ani paket“. Jedná se o přenosy souborů, e-mailů, WWW stránek atd. Záruka se vztahuje na řešení ztrát přenášených paketů, zachování jejich pořadí a odstranění duplikace. Jednotkou posílané informace je na této vrstvě TCP segment.
- UDP – Zajišťuje přenos dat bez záruk, který využívají aplikace, u kterých by bylo na obtíž zdržení (delay) v síti způsobené čekáním na přenos všech paketů a ztráty se dají řešit jiným způsobem (např. snížení kvality, opakování dotazu). Využívá se pro DNS, VoIP, streamované video, internetová rádia, vyhledávání sdílených souborů v rámci sítě DC++, on-line hry atp.

### Relační vrstva
Vrstva č. 5, anglicky session layer. Smyslem vrstvy je organizovat a synchronizovat dialog mezi spolupracujícími relačními vrstvami obou systémů a řídit výměnu dat mezi nimi. Umožňuje vytvoření a ukončení relačního spojení, synchronizaci a obnovení spojení, oznamovaní výjimečných stavů. Do této vrstvy se řadí: NetBIOS, RPC. K paketům přiřazuje synchronizační značky, které využije v případě vrácení paket (např. z důvodu, že se během přenosu dat poškodí síť) k poskládání původního pořadí.

### Prezenční vrstva
Vrstva č. 6, anglicky presentation layer. Funkcí vrstvy je transformovat data do tvaru, který používají 
aplikace (šifrování, konvertování, komprimace). Formát dat (datové struktury) se může lišit na obou 
komunikujících systémech, navíc dochází k transformaci pro účel přenosu dat nižšími vrstvami. Mezi funkce patří např. převod kódů a abeced, modifikace grafického uspořádání, přizpůsobení pořadí bajtů apod. Vrstva se zabývá jen strukturou dat, ale ne jejich významem, který je znám jen vrstvě aplikační. Příklady protokolů: SMB (Samba).

### Aplikační vrstva
Vrstva č. 7, anglicky application layer. Účelem vrstvy je poskytnout aplikacím přístup ke komunikačnímu systému a umožnit tak jejich spolupráci. Do této vrstvy se řadí například tyto služby a protokoly: FTP, DNS, DHCP, POP3,SMTP, SSH, Telnet, TFTP.

## Charakteristika lokálních bezdrátových sítí
Local Area Network (též LAN, lokální síť, místní síť) označuje počítačovou síť, která pokrývá malé geografické území (např. domácnosti, malé firmy). Přenosové rychlosti jsou vysoké, řádově Gb/s. Nejrozšířenějšími technologiemi v dnešních LAN sítích jsou Ethernet a Wi-Fi (nebo také WLAN), v minulosti byly používány např. ARCNET a Token Ring. 

Sítě LAN označují všechny malé sítě, které si mnohdy vytváří sami uživatelé na své vlastní náklady. Jedná se o sítě uvnitř místností, budov nebo malých areálů; ve firmách i v domácnostech. Dále je charakterizuje levná vysoká přenosová rychlost (až desítky Gbps) a skutečnost, že si je na vlastní náklady pořizují sami majitelé propojených počítačů.

Slouží ke snadnému sdílení prostředků, které jsou v LAN dostupné. Nejvyšší podíl při komunikaci v LAN má obvykle sdílení diskového prostoru. Dále LAN umožňuje využívat tiskáren, které jsou připojeny k jiným počítačům nebo vystupují v síti samostatně, sdílet připojení k Internetu a dalších k němu návazných služeb (WWW, E-mail, Peer-to-peer sítě a podobně).

Síť se skládá z aktivních a pasivních prvků. Aktivní prvky se aktivně podílejí na komunikaci. Patří mezi ně například switch, router, síťová karta apod. Pasivní prvky jsou součásti, které se na komunikaci podílejí pouze pasivně (tj. nevyžadují napájení) – propojovací kabel (strukturovaná kabeláž, optické vlákno, koaxiální kabel), konektory, u sítí Token Ring i pasivní hub.

Opačným protipólem k sítím LAN jsou sítě WAN, jejichž přenosovou kapacitu si uživatelé pronajímají od specializovaných firem a jejichž přenosová kapacita je v poměru k LAN drahá. Uprostřed mezi sítěmi LAN a WAN najdeme sítě MAN.


[[Ethernet]]

## Rozdíly TCP a UDP
[[TCP (Transmisson Control Protocol)|TCP]]: 
- spolehlivost – TCP používá potvrzování o přijetí, opětovné posílání a překročení časového limitu. Pokud se jakákoliv data ztratí po cestě, server si je opětovně vyžádá. U TCP nejsou žádná ztracená data, jen pokud několikrát po sobě vyprší časový limit, tak je celé spojení ukončeno. 
- zachování pořadí – Pokud pakety dorazí ve špatném pořadí, TCP vrstva příjemce se postará o to, aby se některá data pozdržela a finálně je předala správně seřazená. 
- vyšší režie – TCP protokol potřebuje např. tři pakety pro otevření spojení, umožňuje to však zaručit spolehlivost celého spojení. 

[[UDP (User Datagram Protocol)|UDP]]: 
- bez záruky – Protokol neumožňuje ověřit, jestli data došla zamýšlenému příjemci. Datagram se může po cestě ztratit. UDP nemá žádné potvrzování, přeposílání ani časové limity. V případě potřeby musí uvedené problémy řešit vyšší vrstva. 
- nezachovává pořadí – Při odeslání dvou zpráv jednomu příjemci nelze předvídat, v jakém pořadí budou doručeny. 
- jednoduchost – Nižší režie než u TCP (není zde řazení, žádné sledování spojení atd.).

## DNS
[[DNS (Domain Name System)]]