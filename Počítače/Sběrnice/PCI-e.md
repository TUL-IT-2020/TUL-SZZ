# PCI-e

[PCI-Express](https://cs.wikipedia.org/wiki/PCI-Express) (též PCIe, PCI-E nebo 3GIO = 3rd Generation I/O) je standard **vysoko rychlostní** (**full duplex**) systémové sběrnice, který byl vytvořen jako náhrada za starší standardy PCI, PCI-X a AGP. Označení sběrnice není zcela správné, protože se jedná o **dvoubodové spoje**, na kterých jsou data přenášena **bez potřeby adresy** (adresace zařízení). Sběrnice PCI-Express používá **sériový přenos** dat (na rozdíl od svých předchůdců), protože to přináší proti paralelnímu přenosu některé výhody, zejména možnost dále zvyšovat frekvenci, na které sběrnice pracuje a tím i přenosovou rychlost.

- <http://vyvoj.hw.cz/teorie-a-praxe/dokumentace/pci-express-obecny-popis.html>
- <http://www.root.cz/clanky/interni-sbernice-pci-express/>
- <https://cs.wikipedia.org/wiki/PCI-Express>
- <http://www.svethardware.cz/technologie-sbernice-pci-express/11606>

Verze        | Kódování  | Přenosová rychlost | Propustnost 1x | Propustnost 4x | Propustnost 8x | Propustnost 16x
------------ | --------- | ------------------ | -------------- | -------------- | -------------- | ---------------
1.0          | 8b/10b    | 2.5 GT/s           | 250 MB/s       | 1 GB/s         | 2 GB/s         | 4 GB/s
2.0          | 8b/10b    | 5 GT/s             | 500 MB/s       | 2 GB/s         | 4 GB/s         | 8 GB/s
3.0          | 128b/130b | 8 GT/s             | 984.6 MB/s     | 3.938 GB/s     | 7.877 GB/s     | 15.754 GB/s
4.0  | 128b/130b | 16 GT/s            | 1.969 GB/s     | 7.877 GB/s     | 15.754 GB/s    | 31.508 GB/s

PCI Express **Link** reprezentuje komunikační kanál mezi dvěma zařízeními sběrnice PCI Express. Základní PCI Express Link je sestaven ze dvou nízkonapěťových diferenciálních párů a to přijímacího a vysílacího komunikačního páru označovaného jako **Lane**. Činnost vysílače i přijímače je na sobě nezávislá a Link tvoří plně duplexní komunikační kanál.

- Základní link se skládá ze dvou jednosměrných diferenciálních párů v každém směru, reprezentující přijímací a vysílací pár. Hodinový signál je kódovaný do datového toku, aby mohlo být dosaženo maximální přenosové rychlosti. Samostatně vedené hodiny a data na vysokých frekvencích jsou náchylné k fázovému posunů a jitteru.
- Každý link může pracovat s příslušnými signálovými úrovněmi pro které byl navržen. Přenosová rychlost dle současné specifikace dosahuje 2,5Gbitu/s na jeden Lane v jednom směru. Zvýšení pracovní frekvence se předpokládá v dalších verzích specifikace.
- Každý Link musí podporovat **alespoň jeden Lane**. Pro zvýšení přenosové rychlosti je možné využít sdružování Lanes do Linků v povolené šířce. Obvykle se jedná o hodnoty **x1, x2, x4, x8, x12, x16 a x32**. Stejná šířka musí byt dodržena jak pro přijímací, tak vysílací část.
- Během hardwarové inicializace Linku se vyjedná pracovní frekvence a počet Lanes sestavujících Link. Obdoba vyjednávání pracovní frekvence sítí typu Ethernet.

- Zajímavé a užitečné je, že i v konektoru ×16 je možné použít kartu, která má menší počet drah (×1, ×2 atd.). Taková karta bude pracovat, i když samozřejmě na nižší rychlosti.*

![Struktura PCI-e](Materiály%20pro%20SZZ/tul-szz-it-nv/28_prumyslove_komunikacni_systemy/28_pcie.png)

_Struktura PCI-e_

Podobně jako sběrnice PCI, tak i sběrnice PCI Express je sestavena ze zařízení, která jsou vzájemně propojena a zajišťují nezbytné funkce sběrnice. Jedné se o zařizení:

- root complex
- switches
- endpoints
- bridges.

Od všech konektorů vedou jednotlivé dráhy do přepínače (switch), který (teoreticky) dokáže libovolné dvě dráhy propojit a vytvořit tak strukturu typu point-to-point. Na jednu stranu je sice nutné, aby byl na základní desce přítomen poměrně složitý přepínač, na stranu druhou však odpadá arbitrážní obvod (který také nebyl zcela jednoduchý) a především: každá dráha může přenášet data maximální rychlostí (samozřejmě obousměrně, čehož se však nedá vždy zcela využít) a zařízení se tak nemusí dělit o jedno přenosové pásmo tak, jak tomu bylo například u sběrnice PCI.
