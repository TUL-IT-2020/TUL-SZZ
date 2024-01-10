# Hodnocení výkonu
Základní požadavek kladený na počítač je schopnost provádět zpracování informací. Tuto schopnost označujeme jako výkonnost počítače. Výkonnost je obtížné hodnotit jediným číslem – objektivnější je použít tzv. vektor výkonnosti, jehož struktura se vyvíjí. Základem bývá počet operací (příp. instrukcí) za sekundu, buď v pevné nebo pohyblivé řádové čárce. Dalšími složkami mohou být propustnost systému, doba odezvy, stupeň využití, aj. Hodnocení výkonnosti by mělo být podkladem pro optimalizaci.

## Metriky výkonosti

- **MIPS** (Million Instructions Per Second)
- **MOPS** (Million Operations Per Second)
- **MFLOPS** (Million FLoating point Operations Per Second)

![Výkonostní metriky](26_metriky.png)
*Výkonostní metriky*

Výjimečně se užívají GIPS (BIPS), GFLOPS, TFLOPS, …

## Výkonostní rovnice

**Výkonnost CPU závisí na:**

- počtu instrukcí (IC – Instruction Count)
- (průměrném) počtu taktů na instrukci (CPI – Cycles Per Instruction)
- periodě hodinového signálu (Tclk) – doba cyklu (taktu)

*Doba provádění programu TCPU je dána počtem hod. cyklů během programu násobená dobou cyklu Tclk (je-li konst.)*

![Výkonostní rovnice](26_vykonostni_rovnice.png)

*Výkonostní rovnice*

**Příklad**

Počítač zpracovává program, který má 5 miliónů 1-CPI (jednotaktových instrukcí), 1 milión 2-CPI a 1 milión 3-CPI. Kmitočet hodinových taktů je 100 MHz. Jaká je jeho výkonnost v MIPS?

![Příklad použití výkonostní rovnice](26_vykonostni_rovnice_priklad.png)

*Příklad použití výkonostní rovnice*

## Amhdahlův zákon
Amdahlův zákon je pravidlo používané v informatice k vyjádření maximálního předpokládaného zlepšení systému poté, co je vylepšena pouze některá z jeho částí. Využívá se např. u víceprocesorových systémů k předpovězení teoretického maximálního zrychlení při přidávání dalších procesorů.

- Úloh, které vyžadují čistě paralelní zpracování, je poměrně málo.
- V praxi jsou nejčastější úlohy, v nichž se střídají úseky výpočtu, který je nutno provádět sekvenčně s úseky vhodnými pro paralelní zpracování.
- Při posuzování účinku paralelizace na výkon systému lze použít analytický vztah, který je podle svého autora Gene Amdahla nazýván zákonem Amdahlovým.
- Předpokládejme, že určitý výpočet lze částečně paralelizovat. To znamená, že kromě části , kterou je nutno provést sériově na jednom procesoru (obvykle vstup a výstup dat, případně jejich předzpracování), lze zbytek výpočtu zadat několika procesorům, tak aby zpracování na nich probíhalo současně.

**Nevýhody**

- Zákon byl formulován v roce 1967
- Má své nedostatky plynoucí hlavně z doby, kdy vzniknul.
- Zákon řeší pouze problém o konstantní velikosti.
- Jinými slovy, paralelní část je fixní.
- S rostoucím počtem procesorů se nemění rozsah problému.
- Nezvažuje vůbec dostupnost výpočetní síly

![Amdáhlův zákon](26_amdahl.png)

*Amdáhlův zákon*

**Zrychlení S** je číslo, které udává kolikrát je rychlejší běh úlohy na počítači s vylepšením oproti běhu stejné úlohy na původním počítači.

![Zrychlení S](26_zrychleni.png)

*Zrychlení S*

**Definujeme poměry**

![Definované poměry](26_pomery.png)

*Definované poměry*

**Doba výpočtu se skládá**

![Doba výpočtu](26_doba.png)

*Doba výpočtu*

**Doba výpočtu na vylepšeném počítači**

![Doba výpočtu](26_doba_vylepsena.png)

*Doba výpočtu na vylepšeném počítači*

**Příklad**

Předpokládejme, že výpočet trvá 30 % času, zbytek času je nevyužit či se čeká na I/O. Dále předpokládejme, že výpočet můžeme 5× zrychlit. Jaká bude celková hodnota zrychlení?

![Doba výpočtu](26_priklad.png)

*Příklad*

Z výpočtu je vidět, že systém bude zrychlen přibližně o 31,6 %.

**Paralelní systém**

Celkové zrychlení výpočtu multiprocesorového systému, který má **p** procesorů, a jehož část programu **fs** může být provedena pouze jediným procesorem (sériová, neparalelizovatelná část), resp. je-li **fp** poměr paralelizovatelné části výpočtu, je dáno:

![Zrychlení multiprocesorového systému](26_amdahl_par.png)

*Zrychlení multiprocesorového systému*

**Příklad paralelní systém**

Jak se zrychlí výpočet dvouprocesorového systému, jestliže 80 % výpočetního algoritmu lze paralelizovat?

![Doba výpočtu](26_priklad_par.png)

*Příklad pro více procesorů*
