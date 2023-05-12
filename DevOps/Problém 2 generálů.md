#CTC
# Problém dvou generálů
Byzantinské chyby
- Problém dvou generálů - Nemá řešení kvůli nespolehlivému komunikačnímu kanálu
	- A: zaútočit za úsvitu
	- B: potvrzuji, zaútočit za úsvitu
	- A: potvrzuji, potvrzuji, zaútočit za úsvitu
	- B: potvrzuji, potvrzuji, potvrzuji, zaútočit za úsvitu ...

Lze vyřešit snížením nejistoty na přijatelnou mez:
- více kurýrů
- potvrzení doručení zprávy

Problém dvou generálů je situace, kdy dva oddělené uzly (např. počítače) musí spolupracovat na rozhodnutí, ale jsou odděleny nespolehlivým komunikačním kanálem, a navíc mohou selhat některé z nich. To znamená, že v takové situaci je nemožné zajistit stoprocentní spolehlivost a jednoznačnost rozhodnutí.

## Volba vůdce
Volba vůdce v Kubernetes se provádí pomocí algoritmu zvaného "leader election". V tomto procesu se uzly v clusteru snaží zvolit jednoho z nich jako vůdce, který bude mít pravomoc koordinovat změny v clusteru. Pokud z nějakého důvodu dojde ke ztrátě vůdce, algoritmus zajistí, že se zbytek clusteru opět spojí a zvolí nového vůdce.

Algoritmus volby vůdce v Kubernetes využívá distribuovaný konsensus algoritmus zvaný Raft. V tomto algoritmu každý uzel v clusteru vytváří replikovaný log a snaží se získat většinu hlasů ze zbytku clusteru. Jakmile uzel získá většinu hlasů, stává se vůdcem a začíná koordinovat změny v clusteru.

### Consensus
V systémech Kubernetes může problém dvou generálů vzniknout například při plánování spuštění kontejnerů na různých uzlech v clusteru. Aby se minimalizovalo riziko vzniku tohoto problému, Kubernetes používá výkonný konsensus algoritmus zvaný Raft.

### Raft
Raft zajišťuje, že v případě selhání uzlu v clusteru, bude jeho role a zodpovědnosti automaticky převedena na jiný uzel, což zaručuje kontinuitu provozu aplikace. Každý uzel v clusteru má svůj vlastní replikovaný log a stává se lídrem, jakmile získá většinu hlasů ze zbytku clusteru. V této roli má pravomoc rozhodovat o změnách v clusteru, jako jsou například plánování spuštění nových kontejnerů nebo odstraňování nefunkčních uzlů.

Tento postup zajišťuje, že každý uzel v clusteru je vždy informován o stavu ostatních uzlů a že rozhodnutí je vždy vykonáno v souladu s plánem clusteru. Tím se minimalizuje riziko vzniku problému dvou generálů a zaručuje se, že aplikace v Kubernetes bude spolehlivě fungovat i při výpadcích jednotlivých uzlů v clusteru.

