## Replikace
Repliky nejsou na stejném uzlu jako primární [[Sharding|shard]]. Zajištuje vysokou dostupnost.

Pro synchronizaci se využívá modelu primary-backup. Automatická distribuce změn v originále do jeho kopií. Slave potvrdí příjem změn, čímž umožní další aktualizace. 

Repliky plně obsluhují dotazy. Zvyšuje se tak propustnost. 

Snapshot - umožnuje obnovu databáze. 