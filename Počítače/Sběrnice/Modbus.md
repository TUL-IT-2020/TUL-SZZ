### Modbus

MODBUS je otevřený protokol pro vzájemnou komunikaci různých zařízení (PLC, dotykové displeje, I/O rozhranní apod), který umožňuje přenášet data po různých sítích a sběrnicích (RS-232, RS-485, Ethernet TCP/IP, MODBUS+ atd.). Komunikace funguje na principu předávání datových zpráv mezi klientem a serverem resp. masterem a slavem. Na sběrnici je jedno „master" zařízení (v případě verze Modbus TCP jich může být více) posílající dotazy, ostatní zařízení jsou „slave". „Slave" zařízení odpovídá na dotazy, které jsou mu adresovány. V pozici mastera je tedy řídící prvek (např. PLC nebo průmyslové PC), v roli slave zařízení jsou ovládané nebo sledované prvky (např. čidla, měřící přístroje, PLC, prvky výrobních linek atp.). Komunikace probíhá metodou požadavek-odpověď a požadovaná funkce je specifikována pomocí kódu funkce jež je součástí požadavku.

- <http://automatizace.hw.cz/clanek/2004082301>
- <http://home.zcu.cz/~ronesova/bastl/files/modbus.pdf>
- <https://cs.wikipedia.org/wiki/Modbus>

**Uzly**

- Master – jediný uzel na sběrnici, nemá přiřazenou adresu, inicializuje přenos
- Slave – 1 až 247 uzlů, každý slave musí mít jedinečnou adresu v rozmezí 1 až 247

  - nemůže vysílat data bez přijetí požadavku od Master uzlu
  - nemůže komunikovat s jiným slave uzlem

Protokol Modbus definuje dva sériové vysílací režimy, Modbus RTU a Modbus ASCII. Režim určuje, v jakém formátu jsou data vysílána. Každá jednotka musí podporovat režim RTU, režim ASCII je nepovinný. Všechny jednotky na jedné sběrnici musejí pracovat ve stejném vysílacím režimu.

- **MODBUS RTU** – V režimu RTU se 8bitový byte vysílá jako jeden znak, integrita zpráv je zajištěna pomocí kontrolního součtu typu CRC a pomocí paritního bitu. Vysílání zprávy musí být souvislé, mezery mezi znaky nesmějí být delší než 1,5 znaku. Začátek a konec zprávy je identifikován podle pomlky na sběrnici delší než 3,5 znaku. Časování a definice protokolu zajišťuje rychlou komunikaci a spolehlivou komunikaci po sběrnici RS485, aniž by byly kladeny přehnané nároky na připojená zařízení. Díky svým dobrým vlastnostem a otevřenosti patří MODBUS RTU k nejrozšířenějším komunikačním standardům pro průmyslovou automatizaci.
- **MODBUS ASCII** – V režimu ASCII je každý 8bitový byte posílán jako dvojice ASCII znaků. Oproti režimu RTU je tedy pomalejší, ale umožňuje vysílat znaky s mezerami až 1 s. Začátek a konec zprávy je totiž určen odlišně od RTU módu. Začátek zprávy je indikován znakem „:" a konec zprávy dvojicí řídicích znaků CR, LF. Tato verze protokolu je tak „lidsky čitelnější", ale proti RTU verzi je málo využívaná.

**Datagram**

![MODBUS datagram](Materiály%20pro%20SZZ/tul-szz-it-nv/28_prumyslove_komunikacni_systemy/28_modbus_datagram.png)

_MODBUS datagram_

V soušasné době jsou implementována MODBUS komunikace po sítích:

- TCP/IP Ethernet
- Asynchronní sériový přenos ( RS - 232C, RS - 422, RS - 485, vlákno, radiový přenos )
- MODBUS PLUS vysokorychlostní síť