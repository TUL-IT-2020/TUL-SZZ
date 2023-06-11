# Počítačové sítě
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

[[Protokol IP (Internet Protocol)]]


## Rozdíly TCP a UDP
[[TCP (Transmisson Control Protocol)|TCP]]: 
- spolehlivost – TCP používá potvrzování o přijetí, opětovné posílání a překročení časového limitu. Pokud se jakákoliv data ztratí po cestě, server si je opětovně vyžádá. U TCP nejsou žádná ztracená data, jen pokud několikrát po sobě vyprší časový limit, tak je celé spojení ukončeno. 
- zachování pořadí – Pokud pakety dorazí ve špatném pořadí, TCP vrstva příjemce se postará o to, aby se některá data pozdržela a finálně je předala správně seřazená. 
- vyšší režie – TCP protokol potřebuje např. tři pakety pro otevření spojení, umožňuje to však zaručit spolehlivost celého spojení. 

[[UDP (User Datagram Protocol)|UDP]]: 
- bez záruky – Protokol neumožňuje ověřit, jestli data došla zamýšlenému příjemci. Datagram se může po cestě ztratit. UDP nemá žádné potvrzování, přeposílání ani časové limity. V případě potřeby musí uvedené problémy řešit vyšší vrstva. 
- nezachovává pořadí – Při odeslání dvou zpráv jednomu příjemci nelze předvídat, v jakém pořadí budou doručeny. 
- jednoduchost – Nižší režie než u TCP (není zde řazení, žádné sledování spojení atd.).


[[DNS (Domain Name System)]]