# CAN

CAN (Controller Area Network) je sběrnice typu multimaster, která je určena k propojování mikropočítačů, různých inteligentních čidel a akčních členů nejen v průmyslu, ale i v automobilech. Její základní koncepce je následující: Jednotlivé stanice připojené na sběrnici vysílají svá data bez ohledu na to, je-li v sytému nějaký „zájemce" nebo nikoliv. Datové rámce proto neobsahují adresu příjemce, nýbrž jen identifikaci která určuje, jaká data rámec obsahuje. Rámec je přijat všemi přijímači na sběrnici. Každý z přijímačů nezávisle použije identifikaci rámce k rozhodnutí, má-li být právě přijatý rámec akceptován, tj. předán k dalšímu zpracování nebo má-li být vymazán.

- <http://home.zcu.cz/~dudacek/NMS/Seriova_rozhrani.pdf>
- <http://vyvoj.hw.cz/navrh-obvodu/rozhrani/aplikovani-sbernice-can.html>
- <https://cs.wikipedia.org/wiki/CAN_bus>

**Vrstvy**

- **Fyzická** a **Linková** vrstva (CAN Bosch)
- **Aplikační** vrstva (CANopen, DeviceNet)

**Linková vrstva:**

- CAN nepoužívá adresu ale identifikátor
- Každý uzel pomocí masky a filtru rozhodne, zda zprávu přijme či nikoli
- Tento způsob umožňuje zasílání zpráv pouze určitým skupinám uzlů
- Různé rámce mají různou prioritu, rámce s větší prioritou se dostanou na sběrnici rychleji a častěji
- **LLC – Logica Link Control**

  - Filtrování zpráv
  - Signalizace přetížení
  - Správa zotavování

- **MAC – Medium Access Control**

  - Zabalení dat do rámce / rozbalení dat z rámce
  - Kódování rámce (vkládání, vyhazování bitu)
  - Řízení přístupu k médiu
  - Detekce a signalizace chyb
  - Správa potvrzování příjmu
  - Serializace / deserializac

**Fyzická vrstva:**

- **PLS – Physical Signaling**

  - Kódování / vzorkování bitu
  - Časování bitu
  - Synchronizace

- **PMA – Physical Medium Attachment** (Charakteristiky budičů)

- **MDI – Medium Dependent Interface** (Konektory, kabely)

Norma pro protokol CAN uvádí dvě specifikace rámců: CAN 2.0A a CAN 2.0B, které se liší v délce identifikátoru. Identifikátor základního formátu CAN 2.0A má délku **11bitů**, identifikátor rozšířeného formátu CAN 2.0B má délku **29bitů**.

Pracuje nad sběrnicí, k níž přistupuje metodou **CSMA/CD+AMP**

- CSMA - náhodný přístup k médiu
- CD - detekce kolizí
- AMP - Arbitration on Message Priority (řidí se prioritami zpráv)

Komunikace na sběrnici CAN probíhá tak, že každý uzel může za určitých okolností využívat sběrnici pro vysílání svých zpráv. Zpráva vysílaná po sběrnici obsahuje identifikační číslo vysílajícího uzlu. Identifikátor definuje nejen obsah zprávy, ale i prioritu přístupu na sběrnici. Tímto způsobem je možno zaslat zprávu z jednoho uzlu do jiného uzlu nebo několik jiných uzlů současně. Komunikační síť CAN může pracovat jak v režimu multi-master (více nadřízených uzlů), nebo v režimu master-slave (jeden uzel nadřízený a více podřízených uzlů).

**Synchronizace se provádí pomocí vkládání bitu:**

- po 5\. bitu jedné úrovně je vložen(navíc) bit opačné úrovně
- po přijetí 5 bitů stejné úrovně musí být přijat bit opačné úrovně a je vyjmut (odstraněn)
- je-li přijat 6\. bit stejné úrovně, je indikována chyba

![Typy CAN](Materiály%20pro%20SZZ/tul-szz-it-nv/28_prumyslove_komunikacni_systemy/28_typy_can.png)

_Typy CAN_

Komunikační protokol CAN definuje formát přenášených zpráv na aplikační úrovni. Zprávy jsou přenášené v tzv. rámcích. V definici CAN jsou určeny čtyři typy rámců:

- datový rámec (DATA FRAME)
- žádost o data (REMOTE FRAME)
- chybový rámec (ERROR FRAME)
- rámec přeplnění (OVERLOAD FRAME)

Datový rámec (**DATA FRAME**) Datový rámec zabezpečuje přenos informací z vysílajícího uzlu všem ostatním uzlům na sběrnici. Tento rámec se skládá z následujících částí:

- START OF FRAME – úvodní jednobitové pole s dominantní hodnotou
- ARBITRATION FIELD – arbitrážní pole sestávající se z identifikátoru a bitu RTR (Remote Transmission Request), který identifikuje, zda-li se jedná o datový rámec (DATA FRAME) nebo žádost o vysílání (REMOTE FRAME). Toto pole určuje prioritu vysílané zprávy. Uzel při vysílání neustále monitoruje stav na sběrnici. Zjistí-li uzel, že vyslal recesní bit a na sběrnici je bit dominantní, okamžitě přestává vysílat. Tímto způsobem je zabezpečeno, aby přistup ke sběrnici dostal ten, jehož zpráva má nejvyšší prioritu. Současně je zabezpečeno, aby při nárůstu zatížení sběrnice nedošlo ke snížení přenosového výkonu sítě.
- CONTROL FIELD – řídící pole, které obsahuje bit IDE (Identifikátor Expresion) pro rozlišení základního a rozšířeného formátu, rezervní bit a 4 bity DLC (Data Length) určující počet byte datového pole (0 až 20 byte). Poměrně malá délka tohoto pole vychází z původního záměru CAN, tj. především zabezpečení rychlého přenosu zpráv s vysokou prioritou. Delší bloky dat je nutno segmentovat v aplikační úrovni. Všechna data na sběrnici jsou dostupná všem uzlům současně.
- DATA FIELD – datové pole o velikosti 0 až 8 bajtů
- CRC FIELD (Cyclic Redundancy Code) – nese 15 kontrolních bitů cyklického redundantního kódu při zahrnutí všech předcházejících polí. Pole je ohraničeno recesivním bitem ERC (END OF CRC)
- ACKNOWLEDGE FIELD – potvrzující pole, které sestává z bitů ACK SLOT a ACK DELIMITER. Vysílač vysílá bit ACK SLOT jako recesivní. Pokud alespoň jeden uzel přijal zprávu bez chyby, přepíše tento bit na dominantní, čímž oznámí vysílači potvrzení příjmu. ACK DELIMITER je recesivní bit, takže ACK SLOT je ohraničen dvěma recesivními bity
- END OF FRAME – konec rámce se skládá z nejméně sedmi recesivních bitů, za nimiž následují nejméně 3 bity pro uklidnění všech vysílačů. V této době mohou přijímací uzly informovat vysílací uzel o chybách přenosu.
- INTERMISSION FIELD + BUS IDLE – mezilehlé pole + uklidnění sběrnice – 3 bity oddělující jednotlivé zprávy

Žádost o rámec (**REMOTE FRAME**) Žádost o rámec má obdobný formát jako datový rámec. Neobsahuje však datové pole a bit RTR je recesivní (v datovém rámci je dominantní). Uzel takto žádá některý jiný uzel na síti o vysílání datového rámce se shodným identifikátorem, jaký je v žádosti.

Chybový rámec (**ERROR FRAME**) Chybový rámec sestává z polí ERROR FLAG a ERROR DELIMITER. Uzel, který zjistí chybu v řetězci přijímaných bitů, začne vysílat 6 dominantních bitů, čímž poruší strukturu rámce. Ostatní uzly začnou též vysílat 6 dominantních bitů. Celková délka ERROR FLAG tak může být 6 až 12 bitů. Za nimi následuje pole ERROR DELIMITER s 8 recesivními bity.

Rámec přeplnění (**OVERLOAD FRAME**) Rámec přeplnění má obdobnou strukturu, jako chybový rámec. Uzel vyšle tento rámec především tehdy, když potřebuje určitý čas na zpracování předchozí zprávy.

**Výhody**

- Vysoká rychlost přenosu dat 1Mbit/s při délce sběrnice do 40m
- Rozlišení zpráv identifikátorem CAN 2.0A 11bitů a CAN 2.0B 29bitů
- Selekce přijímaných identifikátorů zpráv
- Prioritní přístup zabezpečující urychlené doručení významných zpráv
- Diagnostika sběrnice např.: chyba doručení zprávy, chyba CRC, přetečení bufferu
- Značná úroveň zabezpečení přenosu
- Vysoká provozní spolehlivost
- Stále se rozšiřující součástková základna
- Nízká cena

**Nevýhody**

- Omezený počet dat přenášených v rámci jedné zprávy (0 až 8 Byte)
- Prvotní náročnost nastavení registrů CAN sběrnice