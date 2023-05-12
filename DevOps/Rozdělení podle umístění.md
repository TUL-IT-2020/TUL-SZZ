#CTC
# Rozdělení podle umístění
- Privátní – Pouze pro zaměstnance 
- Veřejný – Pro každého, kdo si zaplatí 
- Hybridní – Část privátní a část veřejná 
- Edge – Cílem je přiblížit výpočet/data k uživatelům

## Modely nasazení 
NIST rozlišuje čtyři základní typy modelů nasazení: veřejný cloud, privátní cloud, hybridní cloud a komunitní cloud. Stejně tak jako u distribučních modelů existují ještě některé další modely, které ovšem nejsou tolik běžné.

### Veřejný cloud 
Jedná se o veřejné služby, které jsou dostupné každému na vyžádání. Jsou dostupné buď zdarma nebo je možné si zaplatit větší úložiště nebo výpočetní výkon. Výhodou veřejné cloudu je, že firmy nemusí vynakládat náklady na infrastrukturu, nákup, správu a údržbu. Za veškeré tyto činnosti je zodpovědný poskytovatel dané cloudové služby. Veřejné cloudy mohou být zprovozněny velmi rychle a snadno s velmi nízkými nebo žádnými náklady. Jsou velmi dobře škálovatelné a dostupné pro všechny. Často zmiňovaným rizikem je otázka bezpečnosti. Při správném použití a dodržení postupu je však možné veřejný cloud zabezpečit stejně dobře jako nejlepší privátní implementaci. (Microsoft, 2018) 

#### Výhody veřejného cloudu: 
- **Nižší ceny a nenutnost údržby** – snížení potřeby organizací investovat a udržovat vlastní IT zdroje ve vlastních prostorách.
- **Neomezená škálovatelnost** – je vysoce škálovatelný a díky tomu zvládá nápor a požadavky uživatelů.
- **Efektivita** – snižuje počet promarněných IT zdrojů, protože zákazník si platí pouze za zdroje, které využívá.

Veřejný cloud je plně virtualizované prostředí. Poskytuje multiuživatelskou architekturu, která umožňuje uživatelům sdílet výpočetní prostředky. Data jednotlivých uživatelů jsou oddělena od ostatních uživatelů. Veřejný cloud také spoléhá na vysokorychlostní připojení k internetu, které zajišťuje rychlý přenos dat. Úložiště veřejného cloudu jsou obvykle naddimenzované. Používají několik datových center a důsledně zálohují jednotlivé verze souborů. Z tohoto důvodu jsou považovány za velmi robustní a spolehlivé. (Rouse, 2017) 

### Privátní cloud 
Privátní cloud zahrnuje výpočetní prostředky, které jsou využívány výhradně jednou společností. Privátní cloud bývá obvykle umístěný v datacentru dané organizace nebo může být hostován třetí stranou. Služby a infrastruktura u privátního cloudu jsou vždy spravovány v privátní síti a hardware a software poskytovatele je poskytován výhradně jedné organizaci. Společnost má širší možnosti přizpůsobení výpočetních prostředků svým vlastním IT potřebám. Privátní cloudy jsou obvykle využívány státní správou, finančními institucemi nebo jakoukoliv společností, jenž usiluje o rozšířenou kontrolu nad svými výpočetními prostředky. 

#### Výhody privátního cloudu:
- **Větší flexibilita** – společnost si může přizpůsobit cloudové prostředí k dosažení svých cílů.
- **Lepší bezpečnost** – prostředky nejsou sdíleny s ostatními a je možné dosáhnout vyšší úrovně kontroly a zabezpečení.
- **Vysoká škálovatelnost** – privátní cloudy jsou, stejně jako veřejné cloudy, vysoce škálovatelné a efektivní. (Microsoft, 2018) 

### Hybridní cloud 
Hybridní cloud je kombinací veřejného a privátního cloudu. Veřejný cloud je většinou využíván pro objemná data a nižší potřebu bezpečnosti pro provoz např. webového e-mailu a privátní cloud pro citlivá a pro firmu kritická řešení jako jsou finanční reporty. V hybridním cloudu je možné přesouvat data a aplikace mezi privátním a veřejným cloudem a tím zajistit větší flexibilitu a více možností pro nasazení. 

#### Pro zajištění hybrid cloudu je nezbytné mít k dispozici:
- [[Distribuční modely cloud computingu#IaaS|IaaS]] poskytovatele
- Privátní cloud (vlastní nebo hostovaný)
- WAN spojení mezi těmito dvěma prostředími (Rouse, 2018) 

#### Výhody hybridního cloudu:
- **Kontrola** – organizace si může ponechat privátní infrastrukturu pro citlivá data.
- **Flexibilita** – je možné využít dodatečné výpočetní prostředky ve veřejném cloudu, když jsou potřeba.
- **Cenová efektivita** – s možností škálovatelnosti veřejných cloudů je možné platit za dodatečný výpočetní výkon pouze, když je to potřeba.
- **Jednoduchost** – přesun do cloudu nemusí být obtížný, protože je možné jednotlivé komponenty přesouvat postupně. (Microsoft, 2018)

## Zdroje:
https://dspace.tul.cz/bitstream/handle/15240/152799/DP_Jan_Watzke.pdf?sequence=1&isAllowed=y