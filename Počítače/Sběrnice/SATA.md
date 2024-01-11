# SATA

Serial ATA (SATA) označuje v informatice počítačovou sběrnici, která využívá datové rozhraní pro připojení velkokapacitních paměťových zařízení, jako jsou pevné a optické disky. Délka kabelu je maximálně 1 metr. Topologie je point to point a každé zařízení je připojeno přímo do řadiče. SATA je fullduplexní a poskytuje vyšší výkon díky vestavěnému řadiči DMA.

- <https://cs.wikipedia.org/wiki/SATA>

| Generace SATA | Standard      | Datovápropustnost | Frekvence |
| ------------- | ------------- | ----------------- | --------- |
| 1.            | SATA 1,5 Gb/s | 150 MB/s          | 1,5 GHz   |
| 2.            | SATA 3 Gb/s   | 300 MB/s          | 3 GHz     |
| 3.            | SATA 6 Gb/s   | 600 MB/s          | 6 GHz     |

**Na dohled jsou další revize zohledňující nástup SSD a různých SSDlike mini uložišť, která dále navyšuje podporu a komunikační rychlosti.**

**Již v PATA** (tlustá 40 žil kšanda)

_PIO_ (legacy podpora, nahrazeno DMA)

[PIO](https://cs.wikipedia.org/wiki/PIO) (Programmed Input Output) je režim přenosů dat po sběrnici v počítači mezi periferiemi (CD-ROM, pevný disk, síťová karta apod.) a operační pamětí. Data jsou přenášena za účasti procesoru. Procesor je tedy plně zaměstnán přenosem a nemůže vykonávat jinou práci.

_DMA_

[DMA](https://cs.wikipedia.org/wiki/DMA) (Direct Memory Access) je způsob přímého přenosu dat mezi operační pamětí a vstupně/výstupními zařízeními. Data neprocházejí skrze procesor a lze tak dosáhnout vyššího výkonu (během přenosu dat může procesor zpracovávat jiné strojové instrukce). DMA se používá pro přenos větších objemů dat například řadič pevných disků, grafická karta, síťová karta, zvuková karta a podobně. DMA je odchylkou od Von Neumannovy architektury počítače. DMA je řízené speciálním řadičem, který je součástí základní desky počítače.

**Ve standartu SATA**

_Advanced Host Controler_

SATA řadič využívá jako standardní rozhraní [AHCI](https://cs.wikipedia.org/wiki/AHCI) (Advanced Host Controller Interface), které umožňuje využívat některé pokročilé funkce jako například SATA hotplug a Native Command Queuing (NCQ). Pokud není AHCI povoleno základní deskou nebo chipsetem (resp. nastavením v BIOSu), SATA řadič obvykle pracuje v módu „IDE emulace"

_HotPlug_

Technologie [Hot Plug](https://cs.wikipedia.org/wiki/Hot_swapping) umožňuje odpojit či připojit daný disk i za běhu a v případě podpory i při spuštěném operačním systému.

_NCQ_

[NCQ](https://cs.wikipedia.org/wiki/NCQ) (Native Command Queuing) je technologie, která v některých případech umožňuje zvýšit výkon pevných disků s rozhraním SATA. Při použití NCQ pevný disk sám optimalizuje pořadí, ve kterém jsou vykonány požadavky na zápis nebo čtení. Tato optimalizace může redukovat nadbytečný pohyb hlaviček disku. Tím se zvýší rychlost přenosu dat mezi řadičem a diskem a také se mírně sníží opotřebení disku.

**Specifikace datového vodiče** (SATA specifikuje i speciání napájecí konktor - neuveden)

| Vodič | Funkce  |
| ----- | ------- |
| 1.    | Zem     |
| 2.    | DATA A+ |
|3.    | DATA A-
|4.    | Zem
|5.    | DATA B+
|6.    | DATA B-
|7.    | Zem

Existuje i varianta eSATA pro externí zařízení a eSATAp, která je i napájena.