# Normální formy
Normalizace se provádí za pomoci **normálních forem** (NF). Mezi ně patří:

![http://programujte.com/galerie/2008/07/200807191347_formy.png](http://programujte.com/galerie/2008/07/200807191347_formy.png)

Pozn.: Obecně lze říci, že u každé databáze není nutné aplikovat všechny zde uvedené NF. Vždy záleží na konkrétním uvážení. Nicméně z praktických důvodů se v mnoha případech provádí normalizace alespoň do 3NF.

5NF ∋ 4NF ∋ BCNF ∋ 3NF ∋ 2NF ∋ 1NF

## 1. normální forma
Relace je v první normální formě, pokud každý její atribut obsahuje jen atomické hodnoty. Tedy hodnoty z pohledu databáze již dále nedělitelné.

Následuje příklad na provedení 1NF. Na počátku máme jednu entitu **Osoba** (viz Tabulka 1), která uchovává údaje o osobě. 

| Jméno | Přijmení | Adresa | Telefony |
| --- | --- | --- | --- |
| Jan | Novák | Jana Nováka 2, Praha 1 | 123456789;012345678;789456123 |
| Petr | Holák | Komentského 5, Brno | 159487263;321654987 |
*Tabulka 1: Entita Osoba bez provedení normalizace*

Aby entita *Osoba* byla v 1NF musíme buďto rozdělit atribut telefon do více atributů (pouze za předpokladu, že jsme si jisti, že se množství telefonních čísel nezvýší), nebo oddělit telefoní čísla do samostatné tabulky. V tomto příkladu je zvolen druhý postup, tedy přesun telefonních čísel do samostatné entity **Telefon**. To umožňuje každé osobě přidávat libovolný počet telefonních čísel.

| ID | Jméno | Přijmení | Adresa |
| --- | --- | --- | --- |
| 1 | Jan | Novák | Jana Nováka 2, Praha 1 | 
| 2 | Petr | Holák | Komentského 5, Brno | 
*Tabulka 2: Entita Osoba po převodu do 1NF*

| ID Osoby | Číslo |
| --- | --- |
| 1 | 123456789 |
| 1 | 012345678 |
| 1 | 789456123 |
| 2 | 159487263 |
| 2 | 321654987 |
*Tabulka 3: Entita Telefon po převodu do 1NF*

## 2. normální forma
Relace se nachází ve druhé normální formě, jestliže je v první normální formě a každý neklíčový atribut je plně závislý na primárním klíči, a to na celém klíči a nejen na nějaké jeho podmnožině. Z čehož vyplývá, že druhou normální formu musíme řešit pouze v případě, že máme vícehodnotový primární klíč.

Následuje příklad pro provedení 2NF. V entitě **Sklad** (viz Tabulka 4) je název zboží, výrobce, telefon na výrobce, cena zboží a množství na skladě. Primárním klíčem (PK) této relace je kombinace atributů název a výrobce.

| Název (PK) | Výrobce (PK) | Telefon | Cena | Množství |
| --- | --- | --- | --- | --- |
| Tyčinka milkyway | Milka | +420123456789 | 10Kč | 7000 |
| Mléčná čokoláda | Orion | +420987654321 | 25Kč | 5800 |
*Tabulka 4: Entita Sklad v 1NF*

Telefon výrobce ovšem není závislý na celém klíči, ale pouze na atributu výrobce. To by vedlo k aktualizační anomálii a to k té, že pokud by se vymazaly veškeré výrobky od výrobce Milka, ztratilo by se telefoní číslo na výrobce Milka, což není zrovna žádané. Řešením je opět rozpad na dvě entity - **Výrobek** (viz Tabulka 5) a **Výrobce** (viz Tabulka 6).

| ID Výrobce (PK) | Název (PK) | Cena | Množství |
| --- | --- | --- | --- |
| 1 | Tyčinka milkyway | 10Kč | 7000 |
| 2 | Mléčná čokoláda | 25Kč | 5800 |
*Tabulka 5: Entita Výrobek v 2NF*

| ID Výrobce (PK) | Název | Telefon |
| --- | --- | --- |
| 1 | Milka | +420123456789 |
| 2 | Orion | +420987654321 |
*Tabulka 6: Entita Výrobce v 2NF*

## 3. normální forma
Relace se nachází ve třetí normální formě, splňuje-li předchází dvě formy a žádný z jejich atributů není tranzitivně závislý na klíči. Jiné vyjádření téhož říká, že relace je v 3NF, pokud je ve 2NF a všechny neklíčové atributy jsou navzájem nezávislé.

Volně přeloženo lze říci, že tranzitivní závislost je taková závislost mezi minimálně dvěma atributy a klíčem, kde jeden atribut je funkčně závislý na klíči a druhý atribut je funkčně závislý na prvním atributu.

Následuje příklad pro provedení 3NF. Firma chce uchovávat informace o zaměstnancích v entitě **Zaměstnanec** (viz Tabulka 7).

| ID (PK) | Jméno | Příjmení | Město | PSČ | Funkce | Plat |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Jack | Smith | Jihlava | 58601 | CEO | 150000 |
| 2 | Franta | Vomáčka | Praha 10 | 10000 | Senior Software Architect | 80000 |
*Tabulka 7: Entita Zaměstnanec ve 2NF*

Z entity Zaměstnanec (viz Tabulka 7) je vidět kromě závislosti všech atributů na klíči ještě závislost PSČ a Města a závislost Platu na Funkci. Závislost ID -> Město -> PSČ je tranzitivní závislost PSČ na klíči, stejně tak závislost ID -> Funkce -> Plat. Řešením problému je opět rozpad na více relací, v tomto případě dokonce na 3, protože jsme 3NF porušili rovnou dvakrát. Novými entitami jsou **Město** (viz Tabulka 9) a **Funkce** (viz Tabulka 10).

| ID (PK) | Jméno | Příjmení | Město ID | Funkce ID |
| --- | --- | --- | --- | --- |
| 1 | Jack | Smith | 1 | 1 |
| 2 | Franta | Vomáčka | 2 | 2 |
*Tabulka 8: Entita Zaměstnanec ve 3NF*

| ID (PK) | Město | PSČ |
| --- | --- | --- |
| 1 | Jihlava | 58601 |
| 2 | Praha 10 | 10000 |
*Tabulka 9: Entita Město ve 2NF*

| ID (PK) | Funkce | Plat |
| --- | --- | --- |
| 1 | CEO | 150000 |
| 2 | Senior Software Architect | 80000 |
*Tabulka 10: Entita Funkce ve 2NF*

## Boyce Coddova normální forma (BCNF)
Boyce Coddova normální forma se pokládá za variaci třetí normální formy. Je vymezena stejnými pravidly jako 3NF. Říká, že 3NF musí platit i mezi hodnotami uvnitř složeného kandidátního klíče.

K porušení BCNF (tzn. že relace nebude v BCNF) musejí být splněny podmínky:
- relace musí mít více kandidátních klíčů,
- minimálně 2 kandidátní klíče musí být složené z více atributů,
- některé složené kandidátní klíče musí mít společný atribut.

## 4. normální forma
Relace je ve čtvrté normální formě tehdy, je-li v BCNF a všechny vícehodnotové závislosti obsažené v relaci jsou zároveň funkčními závislostmi. Vícehodnotovou závislost atributů lze definovat následovně: V relaci R, která je v BCNF, s atributy A, B, C nastává vícehodnotová závislost atributu B na atributu A právě tehdy, jestliže množina hodnot B přiřazená dvojici hodnot A, C závisí jen na hodnotě atributu A a je nezávislá na hodnotě atributu C.

## 5. normální forma
Relace je v páté normální formě jestliže je ve 4NF a nemůže být dále bezeztrátově rozložena. Jinými slovy relace, která má n klíčových atributů (n >= 3) a která se rozloží na relace o n-1 klíčových atributech, nemůže být opětovně spojena operací přirozeného spojení do jedné relace, aniž by došlo ke ztrátě informace.

*Konkrétní příklady 4. a 5. formy jsou dostupné na:*

- [http://www.manualy.net/article.php?articleID=13](http://www.manualy.net/article.php?articleID=13)
- [http://programujte.com/clanek/2008071900-normalizace-relacnich-databazi/](http://programujte.com/clanek/2008071900-normalizace-relacnich-databazi/)