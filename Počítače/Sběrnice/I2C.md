### I2C

I2C je zkratka z celého názvu _Inter-Integrated Circuit_. Jedná se o sběrnici typu multimaster, v důsledku čehož se musí řešit arbitrace přístupu na sběrnici. Sběrnice má též zabudovaný mechanismus pro adresování připojených stanic (resp. připojených uzlů). Každá stanice připojená na sběrnici má přidělenu adresu o délce 7 či 10 bitů (slouží k jejímu výběru při komunikaci a při arbitraci). Sběrnice slouží primárně k připojování obvodů k mikrokontrolérům.

**Fyzická vrstva:**
Jednotlivé uzly na sběrnici jsou propojeny právě jedním datovým vodičem značeným SDA. I2C má v celku právě dva vodiče: datový vodič (značen SDA) a vodič s hodinovým signálem (značen SCL). Maximální přípustná frekvence hodinového signálu (SCL vodiče) je 100kHz nebo 400kHz (dle implementace).

**Linková (spojová) vrstva:**
V rámci je obsažena 7 bitová adresa příjemce (adresu má přiřazenu každý uzel na sběrnici) a jeden bit určující typ požadované operace (R/W - read/write). V rámci přenosu dochází k potvrzování přijetí dat (ACK), což se děje paralelně s jejich příjmem. Pokud není přijat ACK, spojení se přerušuje vysláním STOP.

K arbitraci přístupu na sběrnici je využita standardní metoda detekce kolize. Každá stanice může zahájit vysílání, pokud je sběrnice v klidovém stavu. Při vysílání musí docházet ke kontrole, zdali nedochází ke kolizi (jinými slovy, zdali nevysílá více stanic najednou). V případě kolize musí stanice okamžitě ukončit přenos.

**Více na:**

- <http://home.zcu.cz/%7Edudacek/NMS/Seriova_rozhrani.pdf>
- <http://vyvoj.hw.cz/navrh-obvodu/strucny-popis-sbernice-i2c-a-jeji-prakticke-vyuziti-k-pripojeni-externi-eeprom-24lc256>
- <http://www.root.cz/clanky/externi-seriove-sbernice-spi-a-i2c/>
- <https://cs.wikipedia.org/wiki/I%C2%B2C>
- <http://www.root.cz/clanky/komunikace-po-seriove-sbernici-isup2supc/>

**Nejčastěji připojované obvody:**

- Analogové ADC, DAC
- Paměti EEPROM, FLASH
- Řadiče CAN, USB, UART
- Budiče LED, LCD
- CPU supervizory
- RTC obvody
- I/O expandery

**Řízení komunikace**

Pro řízení komunikace se na I2C používá metoda s detekcí kolize. Každá ze stanic může zahájit vysílání, je-li předtím sběrnice v klidovém stavu. Během vysílání musí neustále porovnávat vysílané bity se skutečným stavem SDA. Je-li zjištěn rozdíl mezi očekávaným a skutečným stavem linky SDA, je to indikace kolize mezi několika stanicemi.

**Adresace**

Každá stanice připojená na I2C má přidělenou 7 resp. 10 bitovou adresu. Po zachycení podmínky START porovnávají všechny obvody svou adresu s adresou, která je vysílána na sběrnici. Zjistí-li některý z obvodů shodu, je vysílání určeno právě jemu a musí přijetí adresy potvrdit bitem ACK. Potom přijímá nebo vysílá další data.

**Potvrzování**

Každý vysílaný byte a vyslaná adresa je následována vysláním jednoho bitu ACK. Vysílající stanice jej vysílá v úrovni H. Přijímající stanice potvrzuje přijetí tím, že v době vysílání ACK připojí SDA na úroveň L. Pokud vysílající stanice nedostane potvrzení příjmu, ukončí vysílání podmínkou STOP.

![I2C](Materiály%20pro%20SZZ/tul-szz-it-nv/28_prumyslove_komunikacni_systemy/28_i2c.png)

_Zapojení uzlů na sběrnici I2C_