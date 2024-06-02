# Normalizace, modelování, optimalizace

> Normalizace v relačním modelu, bezztrátová dekompozice, datové modelování (ER/ERA diagramy), funkční analýza (DFD diagramy), optimalizace databázových struktur (typy indexů a případy jejich využití).

## Normalizace v RMD
![[RMD - Normalizace]]

## Bezztrátová dekompozice
**bezztrátová dekompozice** = proces dělení původní relace na více schémat bez ztráty sémantiky 

- spojení tabulek, které vzniknou dekompozicí musí dát přesně původní tabulku (musí se zachovat závislosti)

S dekompozicí se setkáme při normalizování jednotlivých entit.

## Datové modelování (ER diagramy)
![[RMD - Modelování relačního modelu pomocí UML digramu]]

## Funkční analýza (DFD diagramy)
**DFD diagram** = diagram datových toků (data flow diagram) používaný v softwarovém inženýrství pro modelování funkcí systému.

DFD je typicky vícevrstvé. Nejvyšší vrstva zachycuje funkčnost celého analyzovaného problému. Nižší vrstvy se blíže věnují konkrétním částem problému. Počet takto vzniklých vrstev není nikde předepsán, vždy záleží na analytikovi, jakým způsobem analýzu a zpracování DFD zvolí. Obecně je nutné brát v potaz, že DFD slouží jak vývojářům k pochopení problému, tak i pro zákazníka ke specifikaci problému a jeho řešení.

Základní pojmy:
- **proces** - část systému, která mění vstupy na výstupy (symbolem je ovál či kruh),
- **tok** - znázorňuje přesun informací z jedné části systému do jiné (symbolem je šipka),
- **sklad** - slouží k uložení dat k pozdějšímu použití (symbolem jsou dvě vodorovné čáry s pojmenováním),
- **terminátor** - představuje externí entity, které komunikují se systémem a stojí vně systému (symbolem je obdélník).

Chyby, které je nutné při vytváření DFD eliminovat:
- černé díry - proces má pouze vstupy,
- samogenerující fce - proces má pouze výstupy,
- sklady, ve kterých se jen čte nebo zapisuje.

![Ukázka DFD](15_dfd.png)

## Optimalizace databázových struktur
![[Optimalizace databázových struktur]]