# Ethernet 

[Ethernet](https://cs.wikipedia.org/wiki/Ethernet) je název souhrnu technologií pro počítačové sítě (LAN, MAN) z větší části standardizovaných jako IEEE 802.3, které používají kabely s kroucenou dvoulinkou, optické kabely (ve starší verzích i koaxiální kabely) pro komunikaci přenosovými rychlostmi od 10 Mbit/s po 100 Gbit/s. Sítě Ethernet realizují fyzickou a linkovou vrstvu referenčního modelu OSI.

- <https://cs.wikipedia.org/wiki/Ethernet>
- <http://www.svetsiti.cz/clanek.asp?cid=Ethernet-1992000&s=CFE74B0513B385BE1F8FE7EC8CC13A105D7E1A86>

**V jednoduché sítí komunikují všichni na stejné sběrnici (fyzická topologie bus) a řeší se kolize při vysílaní paketů. Situaci zlepšují switche, které pakety filtrují do různých segmentů, aby nedocházelo neustále k blokování.**

**CSMA** (Carrier Sense Multiple Access) - stanice připravená vysílat data si "poslechne" zda přenosové médium (kabel) nepoužívá jiná stanice. V případě, že ano, stanice zkouší přístup později až do té doby dokud není médium volné. V okamžiku kdy se médium uvolní začne stanice vysílat svá data.

**CD** (Collision Detection) - stanice během vysílání sleduje zda je na médiu signál odpovídající vysílaným úrovním (tedy aby se např. v okamžiku kdy vysílá signál 0 nevyskytl signál 1). Případ kdy dojde k interakci signálů více stanic se nazývá kolize. V případě detekce kolize stanice generuje signál JAM a obě (všechny) stanice které v daném okamžiku vysílaly generují náhodnou hodnotu času po níž se pokusí vysílání zopakovat.

**Podvrsty**

- **Logical Link Control (LLC)** – sjednocuje, IEEE 802.2
- **Medium Access Control (MAC)** – konkrétní technologie

**Standardy**

- **10BASE5** Původní Ethernet na koaxiálním kabelu o rychlosti 10 Mbit/s. Koaxiální kabel o impedanci 50 Ω tvoří sběrnici, ke které se připojují pomocí speciálních transceiverů a AUI kabelů jednotlivé stanice.
- **10BASE2** Ethernet na tenkém koaxiálním kabelu o rychlosti 10 Mbit/s. Koaxiální kabel tvoří sběrnici, ke které se připojují jednotlivé stanice přímo. Kabel je impedance 50 Ω (RG-58) nesmí mít žádné odbočky a je na koncích zakončen odpory 50 Ω (tzv. terminátory).
- **10BASE-T** Jako přenosové médium používá kroucenou dvojlinku s rychlostí 10 Mbit/s. Využívá dva páry strukturované kabeláže ze čtyř. Dnes již překonaná síť, která byla ve většině případů nahrazena rychlejší 100 Mbit/s variantou.
- **10BASE-F** Varianta s optickými vlákny o rychlosti 10 Mbit/s. Používá se pro spojení na větší vzdálenost, nebo spojení mezi objekty, kde nelze použít kroucenou dvojlinku. Tvořila obvykle tzv. páteřní síť, která propojuje jednotlivé menší celky sítě. Dnes je již nahrazována vyššími rychlostmi (Fast Ethernet, Gigabit Ethernet).
- **100BASE-TX** Varianta s přenosovou rychlostí 100 Mbit/s, které se říká Fast Ethernet, používá dva páry UTP nebo STP kabelu kategorie 5.
- **100BASE-T2** Používá dva páry UTP kategorie 3, 4, 5\. Je to varianta vhodná pro starší rozvody strukturované kabeláže.
- **100BASE-T4** Používá čtyři páry UTP kategorie 3, 4, 5\. Také vhodná pro starší rozvody strukturované kabeláže.
- **100BASE-FX** Fast Ethernet používající dvě optická vlákna.
- **1000BASE-T** Ethernet s rychlostí 1000 Mbit/s, nazývaný Gigabit Ethernet. Využívá 4 páry UTP kabeláže kategorie 5e, je definován do vzdálenosti 100 metrů.
- **1000BASE-CX** Gigabit Ethernet na bázi měděného vodiče pro krátké vzdálenosti, učený pro propojování skupin zařízení.
- **1000BASE-SX** Gigabit Ethernet používající mnohavidové optické vlákno. Je určen pro páteřní sítě do vzdáleností několik set metrů.
- **1000BASE-LX** Gigabit Ethernet používající jednovidové optické vlákno. Je určen pro větší vzdáleností až několika desítek kilometrů.
- **10GBASE-T** Ethernet s rychlostí 10 Gbit/s, nazývaný Ten Gigabit Ethernet (nebo také EFM – Ethernet on the first mile). Do vzdálenosti 55 metrů lze využít kabeláž kategorie 6\. Pro využití plné délky 100 je nutné použít kategorii 6a (augmented Category 6 – šířka pásma 500 MHz). Někteří výrobci prodávají kabely kategorie 7, které jsou označeny jako kompatibilní s 10GBASE-T. V současné době (rok 2007) je ve vývoji nestíněná varianta UTP kabeláže kategorie 6a.
- **40GBASE** a **100GBASE** s rychlostí 40 a 100 Gbps by měl používat optická vlákna; měděné kabely do délky alespoň 10 metrů

![Ethernetový rámec](Materiály%20pro%20SZZ/tul-szz-it-nv/28_prumyslove_komunikacni_systemy/28_ethernet_frame.png)

_Ethernetový rámec_