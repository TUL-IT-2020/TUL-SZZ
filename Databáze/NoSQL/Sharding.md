#NoSQL 
# Sharding
Databázový vzor pro horizontální [[Škálování|škálování]] na více serverů. 
Záznamy se rozdělí na části (partitions, shards) umístěné na různých serverech. 
Data mezi shardy nejsou sdílena!

Například:
- U relačních databází rozdělení podle řádků.
- U dokumnetovách databází rozdělení podle dokumentů.

## Architektura
Založená na klíči (hash), shard key.

![[Sharding.png]]

Založené na:
- Rozsahu [[DBS - Indexování|indexu]]
- Adresářích (lookup tabulka na shardy)

## Proč shardovat?
- ukládání více dokumentů
- rozdělení velkých indexů
- zlepšení výkonu