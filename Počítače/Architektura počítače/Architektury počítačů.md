# Architektury počítačů
*Architektura počítačů je metoda vytváření počítačových systémů z menších celků.*

Architektura je globální pohled na všechny podstatné vlastnosti počítačů, zahrnuje:
- **strukturu** – popis propojení jednotlivých funkčních bloků
- **organizaci** – popis dynamických interakcí FB a řízení styku mezi nimi
- **realizaci** – popis návrhu a vnitřní struktury jednotlivých FB
- **funkci** – popis chování počítače jako celku

FB - Funkční blok

Procesor (**CPU**) tvoří:
- **ALU** (Arithmetical and Logical Unit) – aritmeticko-logická jednotka
- **CU** (Control / Central Unit) – řadič, řídicí jednotka
- **Registry** (SP, IC, W, Z, ...)

Počítač tvoří:
- CPU
- paměť 
- vstupy/výstupy

Dvě popisované architektury:
- [[Von Neumanovo schéma počítače|Von Neumanovo schéma]]
- [[Harvardské schéma počítače|Harvardské schéma]]
## Von Neumanova koncepce
Charakteristické vlastnosti lze shrnout do následujících bodů:

1. struktura počítače je nezávislá na typu řešené úlohy, počítač se programuje obsahem paměti
2. instrukce a operandy jsou v téže paměti
3. paměť je rozdělena do buněk stejné velikosti, jejich pořadová čísla se používají jako adresy
4. program je tvořen posloupností elementárních příkazů (instrukcí), které se provádějí jednotlivě v pořadí, v němž jsou zapsány do paměti
5. změna pořadí provádění instrukcí se vyvolá instrukcí podmíněného nebo nepodmíněného skoku
6. pro reprezentaci instrukcí i čísel se používají dvojkové signály a dvojková číselná soustava
7. programem řízené zpracování dat probíhá v počítači samočinně (tok dat řídí řadič)
8. zpracování dat probíhá v tzv. diskrétním režimu (během výpočtu nelze s počítačem komunikovat)
9. vstupy (resp. výstupy) jsou koncipovány jako datové zdroje (resp. výsledky) a jsou tedy přímo napojeny na ALU.

**Nevýhodou je možnost mylně interpretovat data jako program.**

![[TUL-SZZ/assets/počítače/26_vonneumann.png]]
*Von Neumannova koncepce*

## Harvardská koncepce
Základní principy (rozdíly vůči von Neumannově archit.):

1. paměť programu je oddělena od paměti dat - možnost ve stejném okamžiku načítat instrukci a přistupovat k datové paměti - datová a programová paměť mohou mít odlišnou organizaci
2. oddělené sběrnice pro program a data
3. řízení procesoru je odděleno od řízení vstupních a výstupních jednotek (nejsou napojeny přímo na ALU)

**Možnost rychlejšího zpracování většího objemu dat.**

![[TUL-SZZ/assets/počítače/26_harvard.png]]
*Harvardská koncepce*

*Rychlé moderní procesory spojují obě architektury. Uvnitř procesoru je použita Harvardská architektura, kde se paměť cache dělí na paměť instrukcí a paměť pro data. Ovšem celý procesor se „z venku“ chová jako procesor s architekturou von Neumannovou, protože načítá data i program z hlavní paměti na jednou.*