# NoSQL databáze
**NoSQL** = Not only SQL database

NoSQL je nerelační systém řízení báze dat navržený pro distribuovaná datová uložiště, nevyžadující pevné předem definované schéma databáze, nepoužívající JOIN operace a horizontálně [[Škálování|škálují]] (při větším vytížení stačí přidat další instanci). 

## Distribuovaná databáze 
Systém, který je složen z několika počítačů a softwarových komponent, které spolu komunikují pomocí počítačové sítě.

Výhody:
- spolehlivost - pokud některý uzel má výpadek, tak to neohrozí funkci celého systému,
- rozšiřitelnost - distribuovaný systém je možné snadno rozšířit přidáním nových serverů,
- sdílení zdrojů - je základní pro mnoho aplikací, data jsou sdílena v distribuovaném systému,
- flexibilita - je snadnější instalovat, implementovat a odladit nové služby,
- rychlost, výkon.

Nevýhody:
- závislost na počítačové síti,
- obecně složitější na správu,
- obecně méně bezpečné než autonomní systémy.

## CAP teorém
![[CAP teorém]]

## Typy NoSQL databází:
- [[Key-value uložiště|key-value uložiště]]
- [[Dokumentové databáze|dokumentové databáze]] ([[MongoDB]], [[Elasticsearch]])
- [[Sloupcové databáze|sloupcová uložiště]] ([[Cassandra]])
- grafová uložiště
- databáze časových řad

![[NoSQL.jpeg]]

![[truth-of-cap-theorem-diagram.webp]]

## Struktura dat
- strukturovaná data
- částečně strukturovaná data
- nestrukturovaná

### Volné schéma
Žádné předdefinované nastavení -> flexibilita.

## Indexování
![[DBS - Indexování]]

## Replikace
![[Replikace]]

## Agregace
Dávkové zpracování dokumentů vracející kompaktní výsledky i po provedení celé řady operací. 

První fáze: Shlukování hodnot z různých dokumentů.
Druhá fáze: provedení operace na shluknutých datech a vrácení výsledku.


