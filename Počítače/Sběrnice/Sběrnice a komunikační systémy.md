# Sběrnice a komunikační systémy

**Průmyslové komunikační systémy** vznikly pro usnadnění řízení rozsáhlých procesů v průmyslu. Patří sem například strojní, letadlový, automobilový, potravinový průmysl atd.

Komunikační systémy pro tato odvětví by měly být:

- **robustní** - decentralizované řešení rozložené po celé "hale"
- **oddolné** - nutné rychlé a bezporuchové měření spolu s ovládáním akčních členů, to i v zarušeném prostředí
- **spolehlivé** - zpravidla nutnost dodržet zpracování v určitém intervalu (worst time)
- **dostupné** - používají se stovky metrů, cena tedy hraje významnou roli
- **flexibilní** - nutnost přizpůsobit systém požadavkům zákazníka

**Standard** nebo také norma je specifikace chování a vlastností, které zaručují kompatibilituu více systémů (různých implementací). Časté jsou různé standardizační komise, které zabraňují drahým vendor lockům.

**Protokol** je konvence nebo standard, podle kterého probíhá elektronická komunikace a přenos dat mezi dvěma koncovými body.

**Sběrnice** je skupina signálových vodičů, kterou lze rozdělit na skupiny řídicích, adresových a datových vodičů v případě paralelní sběrnice nebo sdílení dat a řízení na společném vodiči (nebo vodičích) u sériových sběrnic. Sběrnice má za účel zajistit přenos dat a řídicích povelů mezi dvěma a více elektronickými zařízeními. Přenos dat na sběrnici se řídí stanoveným protokolem.

**Dělení sběrnic**:
- podle provozu
	- **synchronní**
	- **asynchronní**

- podle uspořádání
	- **sériové** (všechny uvedené)
	- **paralelní** (dnes již velmi málo používané)
	- **sérioparalelní**

- podle směru přenosu
	- **jednosměrné**
	- **obousměrné**

- podle umístění
	- **interní**
	- **externí**

**Sériové sběrnice** jsou dnes používány téměř výlučně, důvody k postupnému ústupu paralelních sběrnic jsou v zásadě dva. Synchronizace přenosu jednotlivých bitů paralelně je při vyšších rychlostech a délkách vedení velmi složitá a narážíme zde na technologické limity (viz clock skew), proto může být sériová sběrnice na vyšších taktech paradoxně mnohem rychlejší. Vodiče pro sériovou komunikaci jsou podstatně tenčí a tedy praktičtější na dlouhé rozvody, to následně odráží na výsledné ceně použité kabeláže. Pro realizaci delších sběrnic se jedná o poměrně významný faktor. Pro sériové sběrnice je typická **arbitrace sběrnice** a **paketový systém komunikace**.

## Pomyslné rozdělení uvedených systémů

Uvedená směs sběrnic je hodně různorodá a můžeme jí rozdělit do několika pomyslných skupin podle specifického použití. (moje neoficiální dělení)

- **Průmyslové** ([[CAN|CAN]], [[USART]], RS-485, RS-422, (průmyslový) [[Ethernet přehled|Ethernet]], [[RS-232|RS-232]], [[Modbus]])
	- pracují na vzdálenost desítek metrů
	- nejsou potřeba velké přenosové rychlosti
	- odolné proti rušení (kompromis na úkor přenosové rychlosti)
	- hardware je obvykle odolný na vysoké teploty, prach a elektromagnetické záření
	- povětšinou sériové (dlouhé paralelní sběrnice jsou drahé)

- **Mikrokontrolerové** ([[SPI|SPI]], [[I2C|I2C]])
	- komunikují na krátkou vzdálenost (mezi komponenty na desce nebo mezi systémy)
	- nenáročná implementace a integrace
	- realizováno na jednoduchém hardware
	- obvykle také sériové
	- nejsou potřeba velké přenosové rychlosti
	- obvykle spojené na pevno (nemá konektor)

- **Počítačové** ([[USB|USB]], [[PCI-e|PCI-e]], [[SATA|SATA]])
	- krátká až střední komunikační vzdálenost
	- obvykle velké nároky na přenosovou rychlost

-  **Počítačové historické** ([[IDE]], [[SCSI (Small Computer System Interface)|SCSI]], [[Historické počítačové sběrnice|...]])
	- svého času významné, ale již nahrazené
