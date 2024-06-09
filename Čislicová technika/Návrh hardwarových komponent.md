# Návrh hardwarových komponent
## Slovníček pojmů
- DRL - Dynamically Reconfigurable Logic 
- ASIP - Application Specific Instruction set Processor
- RTL - Register Transfer Level
- Časová doména - část obvodu, jehož registry jsou buzeny stejným hodinovým signálem.
- MTBF - Mean-time-between-failures
- DCM - Digital Clock Manager
- PLD - Programmable Logic Device
- SPLD - Simple PLD
- PAL - Programmable Array Logic
- PLA - Programmable Logic Array
- CPLD - Complex PLD
- FPGA - Field Programmable GateArray
- PSM - Programmable Switch Matrix
- PLL - Phase Locked Loop
- DLL - Delay Locked Loop
- MMAC/s - Million Multiply Accumulates per Second
- CDR - Clock and Data Recovery
- POR - Power On Reset
- NVM - NonVolatile Memory
- RFIC - Radio Frequency IC
- MCU - MicroController Unit
- FPAA - Field Programmable Analog Array
- FPAD - Field Programmable Analog Device
- FPMA - Field Programmable MixedAnalog Digital Array
- EPAC - Electrically Programmable Analog Circuit
- TRAC - Totally Reconfigurable Analog Circuit

## Technologie FPGA

### Programování FPGA

| Technology    | Predominantly associated with ... |
| ------------- | --------------------------------- |
| Fusible-link  | SPLDs                             |
| Antifuse      | SPLDs and CPLDs                   |
| EPROM         | SPLDs and CPLDs                   |
| E2PROM/ FLASH | (some FPGAs)                      |
| SRAM          | FPGAs (some CPLDs)                |

V FPGA se nejčastěji používají programovatelné přepínače na principu:
- **SRAM** (nejčastěji z 5-6 tranzistorů);
- **antipojistky** (anti-fuses) - amorfní křemík v místě křížení dvou vodičů - nevodivá dieletrická vrstva se zvýšeným napětím prorazí (odpor 100MΩ/50Ω); PLICE (Actel), ViaLink (QuickLogic);
- **EEPROM**/**flash**- u FPGA v omezené míře.

| Vlastnosti                           | SRAM                        | Antipojistky | EEPROM/flash                        |
| ------------------------------------ | --------------------------- | ------------ | ----------------------------------- |
| Reprogramovatelnost                  | ano (v systému)             | ne           | ano (v systému nebo v programátoru) |
| Volatilní (nutné napájení)           | ano                         | ne           | ne                                  |
| Vyžaduje externí konfigurační soubor | ano                         | ne           | ne                                  |
| Ochrana proti kopírování             | vyhovující (lze zašifrovat) | dobrá        | dobrá                               |
| Velikost konfigurační buňky          | velká (5 tranzistorů)       | velmi malá   | malá (2 tranzistory)                |
| Spotřeba el. energie                 | vyšší                       | nízká        | střední                             |
| Odolnost vůči záření                 | horší                       | výborná      | střední                             |
| Okamžitě použitelné                  | ne                          | ano          | ano                                 |
| Programování v systému               | ano                         | ne           | ano                                 |

### Použití RAM v FPGA 
1) **Klopné obvody** v logických buňkách (pro menší množství dat, rychlý přístup); 
2) **Distribuovaná paměť** - využití paměťových buněk v LUTech (omezená velikost, náročné na propojovací sítě); 
3) **Bloková** (embedded) paměť - speciální paměťové bloky vložené do struktury FPGA (snadno konfigurovatelné, plně dvouportové, rychlé, efektivní z hlediska nároků na plochu); 
4) **Externí paměti** - pro uložení velkých objemů dat (nejčastěji dynamické paměti, podpora DDR řadičů v FPGA).

### DSP bloky
Speciální bloky optimalizované na DPS aplikace (FIR, FFT,…). Jsou složeny z násobiček, sčítaček (příp. odečítaček) a registrů. Jednotlivé bloky jsou mezi sebou vzájemně provázané. Operace převážně ve formátu pevné řádové čárky.

#### Výkon FPGA (DSP bloků)
MMAC/s (Million Multiply Accumulates per Second) pohybuje se v rozmezí řádově od 101 do 104 (milion násobení a mezisoučtů za sekundu).

## Metodika návrh
### Úrovně abstrakce
- Behaviouristická úroveň 
  - popis chování systému na vyšší úrovni abstrakce,
  - volba algoritmů a architektury (neuvažujeme detaily); 
- Úroveň FB (RTL - Register Transfer Level)
  - popis tokem dat (stavový diagram)
  - FB: logické operátory, RAM, DSP, multiplexory, čítače, ...
  - Nejčastěji používaná úroveň ve VHDL a Verilog HDL;
- Úroveň logického schématu- popis na úrovni hradel,
  - jednoznačný přechod na úroveň tranzistorů,
  - často již hardwarově závislé (pro konkrétní FPGA);
- Úroveň strukturální- vzájemné propojení jednotlivých funkčních bloků či knihoven,
  - omezení možností syntézy či optimalizace.

### Postupy systémového návrhu
**Zdola-nahoru** (bottom-up)
- systém skládáme z hotových FB
- vhodné pro menší systémy,
- menší nároky na zkušenosti (ověřené FB),
- výsledné řešení méně optimální.

**Shora-dolů** (top-down) 
- koncepci rozvádíme do podrobností
- vhodné pro velké systémy, 
- dosažení lepšího výsledku,
- náročné na zkušenosti.

### Technika zřetězení (pipelining)
Umožňuje zvyšování pracovního kmitočtu v systému.
### Synchronizace registrů (retiming)
Vyrovnání kombinačních logických cest mezi registry.

- Replikace a rozmístění registrů do míst, kde jsou cílové obvody.

### Synchronní návrh
Ideální je vše taktovat jedněma hodinami. 

### Metastability
Metastabilitou nazýváme neschopnost výstupu registru ustálit se na definované logické úrovni v přesně definovaném čase, obvykle za jednu hodinovou periodu. 

Důsledkem metastabilit mohou vznikat:
- proudové špičky na napájení, 
- nekorektní přechody mezi stavy stavových automatů,
- nekorektní hodnoty na sběrnicích.

#### Synchronizátory
Pro snížení pravděpodobnosti vzniku metastability se používají dvojnásobné (výjimečně i trojnásobné) synchronizátory (synchronizační buňky) - pro jednotlivé signály.

### Makrobloky, jádra (cores)
Makro je definováno jako část navrhovaného systému, která je použitelná jako samostatný stavební blok. Používání maker výrazně zkracuje a zlevňuje návrh.

Dva typy makrobloků:
- soft core - forma syntetizovatelného RTL kódu,
- hard core - výstupem je hotový layout/netlist (závislé na technologii).

IP bloky - navržené makrobloky, často nutné zakoupit licenci (Intellectual Property- intelektuální vlastnictví).
## I/O
Buňky jsou rozděleny do bank, každou banku lze připojit na jiný napájecí zdroj.

Většina buněk může být konfigurována jako vstupní, výstupní nebo obousměrné.
### Ošetření vstupů

> [!info] Ochrana proti zákmitům.
>1. Signál proženeme klopným obvodem typu D s výrazně pomalejšími hodinami. 
>2. Následně stavový automat s hladinovým trigrem co generuje pulz délky jednoho času.

### Napájecí napětí 
Napájení se rozděluje do 3 skupin:
- napájení vlastního jádra s log. bloky,
- napájení vstupně-výstupních buněk (1,2 - 3,3 V),
- napájení speciálních bloků (např. fázové závěsy). 

Napětí jádra souvisí s výrobní technologií: 
- 3,3 V (350 nm), 
- 2,5 V (220 nm), 
- 1,8 V (150 nm), 
- 1,5 V (130 nm), 
- 1,2 V (90 nm), 
- 1,0 V (65 nm), 
- 0,9 V (40 nm), 
- 0,85 V (28 nm).

### Standardy vstupů a výstupů
Single-Ended I/O:
- LVTTL (3.0V/2.5V/1.8V)
- LVCMOS (3.0V/2.5V/1.8V/1.5V/1.2V)
- PCI (Peripheral Component Interconnect)
- PCI-X (PCI Extended)

Differential I/O:
- LVDS (mini-LVDS, BLVDS)
- SSTL (3V/2V/1.8V) - Series Stub Terminated Logic
- HSTL (1.8V/1.5V/1.2V) - High-Speed Transceiver Logic
- LVPECL - Low Voltage Positive Emitter Coupled Logic
- RSDS - Reduced Swing Differential Signaling
- PPDS - Point-to-Point Differential Signaling

### Protokoly komunikace
Sériové diferenční linky:
- Serial Rapid IO (sRIO),
- PCI Express (v. 1.1 a 2.0),
- Ethernet (0,1 - 1 - 10 Gbps),
- USB (v. 2.0 a 3.x).

