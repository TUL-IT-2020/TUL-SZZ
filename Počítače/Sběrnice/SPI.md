# SPI

Sběrnice SPI (_Serial Peripheral Interface_) představuje jednu z forem sériových externích sběrnic sloužících pro vzájemné propojení dvou či více komunikujících uzlů, přičemž jeden uzel obvykle vystupuje v roli takzvaného řadiče sběrnice (**master**), ostatní uzly pracují v režimu **slave**. Uzel, který pracuje jako master, obsahuje generátor hodinového signálu, který je rozveden do všech ostatních uzlů, čímž je umožněn zcela synchronní (navíc ještě obousměrný) přenos dat. Hodinový signál je rozváděn vodičem označovaným symbolem **SCK**. Kromě vodiče s hodinovým signálem jsou uzly propojeny dvojicí vodičů označovaných většinou symboly **MISO** (Master In, Slave Out) a **MOSI**(Master Out, Slave In), pomocí nichž se obousměrně (**full duplex**) přenáší data. Posledním signálem, který se u této sběrnice používá, je signál **SSEL** (Slave Select), jenž slouží – jak již jeho název napovídá – k výběru některého uzlu pracujícího v režimu slave. V následujících kapitolách si ukážeme, jak a kdy se tento signál používá. Všechny čtyři signály – **SCK**, **MISO**, **MOSI** i **SSEL**, pro svoji funkci vyžadují pouze jednosměrné porty, což přispívá k jednoduché a především levné implementaci této sběrnice.

- oddělený datový signál mastera od datového signálu slave (MOSI, MISO) (full-duplex)
- sériové, synchronní
- mono-master(jeden master, více slavů)
- 2 konfigurace(nezávislá, kaskádová)

- <http://www.root.cz/clanky/externi-seriove-sbernice-spi-a-i2c/>
- <https://cs.wikipedia.org/wiki/Serial_Peripheral_Interface>
- <http://home.zcu.cz/~dudacek/NMS/Seriova_rozhrani.pdf>

**Obvody:**

- Analogové ADC, DAC
- Paměti EEPROM, FLASH
- Řadiče CAN, USB, UART
- Budiče LED, LCD
- CPU supervizory
- RTC obvody

![SPI více násobné](Materiály%20pro%20SZZ/tul-szz-it-nv/28_prumyslove_komunikacni_systemy/28_spi_vicenasobne.png)

_Způsob komunikace s více zařízeními pomocí výběru uzlu signálem SSEL. Čím více existuje uzlů typu slave, tím větší množství pinů CSx je nutné použít. Vzhledem k tomu, že v danou chvíli může být vybrána jen jedna komunikující dvojice uzlů, lze mezi uzel typu master a ostatní uzly vložit demultiplexor pracující v režimu výběru „jedna z n"._

![SPI zřetězení](Materiály%20pro%20SZZ/tul-szz-it-nv/28_prumyslove_komunikacni_systemy/28_spi_zretezeni.png)

_Propojení zařízení do řetězu (daisy chain) vede ke snížení požadovaného počtu vodičů, ale také k prodloužení cesty (a tím i času) dat při jejich vysílání a příjmu. V případě, že jedno z připojených zařízení nebude funkční, celý řetězec se rozpadne._