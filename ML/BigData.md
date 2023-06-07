# Big Data
Datasety tak velké, že je nemožné/obtížné s nimi pracovat za pomoci tradičních nástrojů a DB (převážně relačních) v rozumném čase. 

> „Soubory dat, jejichž velikost je mimo schopnosti zachycovat, spravovat a zpracovávat data běžně používanými softwarovými prostředky v rozumném čase.“
> -  Gartner

### Charakteristiky Big Data
3V big dat:
- **Volume** (obsah): data nejsou pouze text, exponenciální nárůst objemu.
- **Velocity** (rychlost): rychlost, kterou data přibývají, nebo rychlost zpracování dat.
- **Variety** (různorodost): data nemají homogenní strukturu, počet forem stále roste.

Další "Vé":
- **Veracity** (věrohodnost): zaujatost, šum, abnormality v datech.
- **Valence** (valence): propojovatelnost dat formou grafů (vnitřní podobnost).
- **Value** (hodnota): jak z těchto dat získat nějakou hodnotu?

## Aplikace Big Data
Analýza big data:
- Kvalitnější modely
- Odporučovací systémy
- Cílený marketing
- Pochopení potřeby zákazníka
- analýza sentimentu
- reklama závislá na poloze
- medicína
- big data měst


Cílený marketing
Využívají navštívených stránek, historie vyhledávání, objednávek, sociální média.
Google adds

Odporučovací systémy
Na základě předchozí aktivity uživatele. Netflix, Steam, Amazon, Sociální sítě (TikTok, Redit).
Cílem je doporučení ideálního produktu.

Chování skupiny
Sezónnost nabídky. Letecké společnosti.

Města
Úspora energie, menší zácpy, predikce kriminality. 


## Odkud Big Data pochází?
Tři hlavní zdroje:
- **stroje** (senzory)
- **lidi** (sociální sítě, blogy)
- **organizace** (transakce v databázích)

### Strojová data
Největší zdroj Big Dat. 
Zpracovávání v reálném čase -> detekce podvodů, monitorování systémů. 
Microsoft Azure, Amazon web services

#### Chytrá zařízení
Měří a produkují Big Data. Jsou navzájem propojená. Autonomní sběr a nalýza dat. IoT - internet věcí. 
Například: chytré hodinky

### Lidská data
Facebook, Twiter, Instagram, blogy, vyhledávání, textové zprávy, emaily.

Většina dat je textových a nestrukturovaných. 

Využití NErealčních databází. 
NoSQL databáze: 
- [[Apache Hadoop|hadoop]], 
- [[Apache Spark|Spark]], 
- [[Cassandra|Cassandra]].

### Organizační data
Důvěryhodná data: transakce, kreditní karty, bankovnictví, akcie, zdravotní záznamy, senzory,...
Vysoce strukturovaná data. Uloženo v relačních databází (+SQL).

## Struktura Dat
Data mou být:
- strukturovaná, 
- částečně strukturovaná, 
- nestrukturovaná.

### Strukturovaná data
Informace uložené v definovaném datovém modelu. Umožnují snadný přístup a čtení. Snadno se analyzují. Uložené například v relačních databázích (relace, atributy). 

### Nestrukturovaná data
Data v nezpracované podobě, nemají žádný specifický formát. Obtížné na zpracování kvůli komplexnosti a složitosti. 

Různé podoby:
- sociální media (příspěvky),
- chaty,
- satelitní snímky,
- prezentace.

### Částečně strukturovaná data
Například digitální fotografie a metadaty jako jsou například typu datum místo pořízení a ID zařízení. 

## Analýza velkých dat

Integrace
Hlavní přínos Big Data je v integraci rozličných dat. Přeměna dat r zůrných zdrojů na jednoutnou a užitečnou informaci. 
- Snížení komplexity dat,
- zvýšení dostupnosti,
- sjednocený datový systém.

Využití [[Cloud|Cloud computingu]] a [[Distribuovaný systém|distribuovaných systémů]]. Analýza enormních dat za pomoci výpočetního výkonu serverů. [[Distribuční modely cloud computingu|Distribuční model]] pro cloud computing.