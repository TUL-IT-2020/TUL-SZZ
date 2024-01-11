# Architektura procesoru
Procesor se skládá z:
- **řídicí jednotky** CU (Control Unit) – řadič
- **aritmeticko-logické jednotky** ALU (Arithmetic Logic Unit)
- **sady registrů** RS (Register Set), které uchovávají různé hodnoty během práce počítače (zápisníková paměť) ALU + RS je někdy označuje jako operační jednotka
- **programového čítače** PC (Program Counter) – často se uvádí jako jeden registr RS nebo součást řadiče
- **vnitřní sběrnice** - řeší spojení mezi bloky CPU (typy - datová, adresová, řídicí), od každého typu může být v architektuře i více sběrnic

![Model Procesoru](TUL-SZZ/assets/počítače/26_model_procesoru.png)
*Model Procesoru*

**Rozlišujeme 2 koncepce řadičů (CU):**
- řadič je speciální sekvenční automat, který má čítač a dekodér (je dražší, ale rychlejší) – obvodový řadič (založen na kombinačních logických obvodech)
- dekódování operačního znaku vykonává řídicí paměť, ve které jsou mikroprogramy uloženy – mikroprogramový řadič (založen na výběru z paměti ROM).

## Kategorie procesorů:
- Univerzální (Intel, AMD, …)
- [[Architektura grafických procesorů|Grafické]] (Nvidia, ATI, …)
- [[Architektura signálových procesorů|Signálové]] (TI, AD, …)
- Aplikační (pro mobilní telefony, …)
- Multimediální (TI, Mpact, …)
- Speciální (šifrovací, kompresní, hrací, …)

## Architektura souboru instrukcí (ISA)

Souhrn vlastností počítačového systému viděného z pohledu programátora v strojovém jazyce (koncept struktury, funkčního chování)

### Skládá se z:
- seznamu instrukcí procesoru
- datových typů
- dostupných režimů, jež jsou k dispozici
- seznamu registrů
- pravidel pro manipulaci s výjimkami a přerušeními

### Dělíma na:
- **Střadačově orientovaná ISA** (dominantní střadač - akumulátor)
- **Zásobníkově orientovaná ISA** (vše se děje přes zásobník)
- **ISA s univerzálními registry** (nejpoužívanější architektura, mnoho univerzálních registrů)

### Instrukční cyklus:
- **IF** - načtení instrukce (instruction fetch)
- **ID** - dekódování (instruction decode)
- **OF** - načtení operandů (operand fetch)
- **EX** - vykonání operace (execution)
- **MEM** - obsluha paměti (memory)
- **WB** - zápis výsledku (write back)

### Vývoj procesorů lze rozdělit do několika fází:
- **Subskalární procesory** (Tradiční sekvenční provádění instrukcí.)
- **Skalární procesory** (Sekvenční zpracování částečně nahrazeno zpracováním paralelním (např. zřetězené zpracování, či několik jednotek), v každý okamžik se dokončí jen jedna instrukce.)
- **Superskalární procesory** (Umí dokončit více instrukcí za jeden cyklus.)

## Procesory dělíme podle instrukční sady na:

### [[CISC|CISC]]
**Complex Instruction Set Computer**, má rozsáhlý instrukční soubor, obsahuje i mnoho složitých instrukcí (z hlediska HW) používaných jen zřídka.

- proměnná délka instrukcí
- zpracování instrukcí ve více strojových cyklech (CPI ~ 5-10)
- velký počet adresovacích módů
- díky vysoké složitosti byl řadič navržen na principu paměti s mikroprogramy (ROM)
- řídicí obvody zabírají na čipu přibližně 60% místa
- pro překlad programů bývá zpravidla jednodušší překladač
- používá se zpravidla GPR ISA (varianta R-M, M-M)
- s postupem doby se začíná používat zřetězené zpracování (zejména s rozkladem na mikroinstrukce) - pipeline

### [[RISC|RISC]]
**Reduced Instruction Set Computer**, (použit poprvé 1974) počátkem 80.let první RISC procesory. Snaha přesunout některé složité a zřídka používané CISC instrukce z mikroprogramů do programů (zvětšení počtu instrukcí v programu, ale snížení CPI).

- malý počet relativně jednoduchých instrukcí (důležitý není až tak počet, ale jednoduchost v požadavku na HW) (asi 40–150)
- jednoduché instrukce umožňují vyšší frekvenci
- implementováno proudové zpracování instrukcí - v každém taktu se většinou dokončí jedna instrukce (CPI < 1,5)
- instrukce mají většinou pevnou délku a malý počet formátů,
- řadič s pevnou logikou místo mikroprogramování (rychlé)
- řídicí obvody zabírají pouze 6–10 % místa (obvodový řadič)
- velký počet programově dostupných registrů (32–192)
- operace s daty pouze nad registry (2 zdrojové, 1 cílový)
- registry jsou víceúčelové (jednodušší překladače)
- přístup do paměti pouze pomocí instrukcí přesunu (mluvíme o architektuře L/S – instrukce Load a Store)
- malý počet adresových módů (3–5)
- ortogonální instrukční soubor (ve všech instrukcích, které používají registr procesoru jako zdrojový nebo cílový operand, lze použít libovolný registr)
- pro zvýšení účinnosti pipeline optimalizující kompilátor pro naplánování instrukcí
- nejčastěji [[Harvardské schéma počítače|harvardská architektura]]

### PostRISC (CRISC)

*Do této kategorie je možné zařadit většinu současných CPU*

- kombinace CISC a RISC (navenek CISCové, ale vnitřní konstrukci mají RISCovou)
- instrukce trvají různě dlouhou dobu
- instrukce se rozloží na jednoduché mikroinstrukce
- proudové zpracování mikroinstrukcí
- větší množství paralelních operací
- spekulativní provádění instrukcí
- nadále dochází k dalšímu rozšiřování instrukční sady, zaměřené hlavně do multimediální oblasti a grafiky
- většinou se zachovává zpětná kompatibilita

### Praktický rozdíl mezi CRISC a RISC

Procesory od Intel, AMD jsou CRISC, zatímco ARM (v mobilních zařízeních) jsou RISC. Díky jednoduchosti RISC architektury (řídících obvodů na procesoru) je možné dosáhnout mnohem menší spotřeby než u CRISC.