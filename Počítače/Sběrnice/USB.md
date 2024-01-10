### USB

USB (Universal Serial Bus) je univerzální sériová sběrnice, moderní způsob připojení periferií k počítači. Nahrazuje dříve používané způsoby připojení (sériový a paralelní port, PS/2, Gameport apod.) pro běžné druhy periférií. USB je sběrnice jen s jedním zařízením typu Master, všechny aktivity vycházejí z PC a je možné připojit až 127 různých zařízení. PC může požadovat data od libovolného zařízení, naopak žádné zařízení nemůže vysílat data samo od sebe. Veškerý přenos dat se uskutečňuje v tzv. rámcích, které trvají přesně 1 milisekundu. Uvnitř jednoho rámce mohou být postupně zpracovávány pakety pro několik zařízení. Přitom se mohou spolu vyskytovat pomalé (low-speed) i rychlé (full-speed) pakety. Rozhraní obsahuje 5V napájení a maximální proud 100mA, na požádání 500mA: Některé desky mají napájení přímo ze zdroje a není limitováno specifikací. Maximální délka kabelu je 5m.

- <http://vyvoj.hw.cz/navrh-obvodu/rozhrani/rs-485-rs-422/usb-20-dil-1.html>
- <http://vyvoj.hw.cz/navrh-obvodu/rozhrani/rs-485-rs-422/usb-20-dil-2.html>
- <http://www.root.cz/clanky/universalni-seriova-sbernice-usb/>
- <https://cs.wikipedia.org/wiki/Universal_Serial_Bus>

Specifikace USB obsahuje čtyři základní typy datových přenosů:

- **Řídící** (control) přenosy jsou používány ke konfiguraci zařízení při jeho připojení a mohou být použity k dalším účelům, jako např. k řízení dalších komunikačních rour.
- **Hromadné** (bulk) přenosy slouží k přenosům velkého množství dat a jsou na ně kladena nejmenší omezení.
- **Přerušovací** (interrupt) přenosy slouží k včasnému a spolehlivému doručení dat, nejčastěji pro asynchronní události.
- **Izochronní** (isochronous) přenosy zabírají předem smluvené množství přenosového pásma a mají předem dohodnuté zpoždění. Tento druh přenosů je také nazýván proudový přenos v reálném čase (streaming real-time transfer).

![USB topologie](Materiály%20pro%20SZZ/tul-szz-it-nv/28_prumyslove_komunikacni_systemy/28_usb_topologie.png)

_USB topologie_

**Plug and Play**

Výhodou je možnost připojování Plug and Play bez nutnosti restartování počítače nebo ručního instalování ovladačů. Zařízení lze připojit za chodu k počítači a během několika sekund je přístupné. Při připojení nového zařízeni nejprve hub podle zdvižené datové linky pozná, že se objevilo nové zařízení. Pak proběhnou následující kroky:

- Hub informuje hostitelský počítač o tom, že bylo připojeno nové zařízení.
- Hostitelský počítač se dotáže hubu, na který port bylo zařízení připojeno.
- Po doručení odpovědi vydá počítač příkaz tento port zapnout a provést vynulování (reset) sběrnice.
- Hub vyrobí nulovací signál (reset) o délce 10 ms. Uvolní pro zařízení napájecí proud 100 mA. Zařízení je nyní připraveno a odpovídá na implicitní (default) adrese.
- Než zařízení USB obdrží svou vlastní adresu sběrnice, je možno se na ně obracet přes implicitní adresu 0\. Hostitel si přečte první bajty popisovači zařízení, aby stanovil, jakou délku mohou mít datové pakety.
- Hostitel přiřadí zařízení jeho adresu na sběrnici.
- Hostitel si ze zařízení pod novou sběrnicovou adresou načte všechny konfigurační informace.
- Hostitel přiřadí zařízení jednu z možných konfigurací. Zařízení nyní může odebírat tolik proudu, kolik je uvedeno v jeho popisovači. Tím je připraveno k použití. Hostitel přiřadí zařízení jeho adresu na sběrnici.

**Vodič**

1    | Vcc        | napájení
---- | ---------- | ---------------------------------------------
2    | D-         | rozdílový pár USB 2.0
3    | D+         | rozdílový pár USB 2.0
4    | GND        | zem napájení
5    | StdB_SSTX- | superrychlostní vysílač diferenciálního páru
6    | StdB_SSTX+ |
7    | GND_DRAIN  | zem signálu
8    | StdB_SSRX- | superrychlostní přijímač diferenciálního páru
9    | StdB_SSRX+ |
kryt | stínění    | kryt

**Rychlosti**

Standart      | Rychlost
------------- | --------------------------
USB 1.1       | 12 Mbit/s
Firefire 400  | 400 Mbit/s
USB 2.0       | 480 Mbit/s
FireWire 800  | 800 Mbit/s
USB 3.0       | 5 Gbit/s
USB 3.1       | 10 Gbit/s
eSATA         | Up to 6 Gbit/s (750 MB/s)
Thunderbolt   | 10 Gbit/s × 2 (2 channels)
Thunderbolt 2 | 20 Gbit/s
Thunderbolt 3 | 40 Gbit/s

_Přichácí USB-C, v podstatě USB 3.1 s jinným konektorem a podporou pro velké proudy (3A), vhodné třeba pro napájení notebooku._