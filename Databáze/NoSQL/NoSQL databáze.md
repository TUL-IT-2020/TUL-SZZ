# NoSQL databáze
**NoSQL** = Not only SQL database

NoSQL je nerelační systém řízení báze dat navržený pro distribuovaná datová uložiště, nevyžadující pevné předem definované schéma databáze, nepoužívající JOIN operace a horizontálně škálují (při větším vytížení stačí přidat další instanci). 

### Distribuovaná databáze 
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

### Škálování
Schopnost přidat vlastnosti, aby byly uspokojeny nové nároky uživatelů.

- **vertikální škálování** - přidání zdrojů do již existujícího systému, aby se zvýšila jeho kapacita, průchodnost atd. (např. přidat procesor, paměť, ...)
- **horizontální škálování** - přidání nových uzlů (např. nový počítač do již existující infrastruktury)

### CAP teorém
![[CAP teorém]]
