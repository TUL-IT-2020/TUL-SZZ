# Sekvenční obvody
**Sekvenční obvody** jsou elektronické obvody, které mají paměť a udržují informaci o předchozím stavu vstupů.

# Klopné obvody #klopné_obvody
- Klopné obvody jsou základními stavebními bloky sekvenčních obvodů.
- Mají dva stavy: SET (nastaven) a RESET (vynulován).

## RS (Reset-Set)
Má dva vstupy (R a S) pro nastavení a resetování. Může se nacházet ve stavu SET, RESET nebo stabilním stavu
![[Synchronní RS klopný obvod.png]]
## JK
Kombinuje vlastnosti RS a D klopného obvodu, umožňující univerzální chování s pomocí tří vstupů (J, K a CLK)
![[JK klopný obvod.png]]
## D (Data) a T
Má jeden vstup pro zápis dat a dva hodinové vstupy (CLK a CLR). Umožňuje ukládat a aktualizovat hodnoty v závislosti na hodinovém signálu.
![[D a T klopný obvod.png]]

# Registry #Registry
![[Registry.png]]

## Posuvné registry
![[Posuvný registr.png]]
# Čítače #Čítače
## Synchronní Čítače
Každý přechod na nový stav čítače je synchronizován hodinovým signálem (CLK). Hodnoty v čítači jsou aktualizovány pouze na hraně hodin.
## Asynchronní Čítače
Přechody do nových stavů jsou řízeny vnitřními hodinovými signály a nemusí být synchronizovány s vnějším hodinovým signálem.
# Návrh Automatů typu Mealy a Moore

## Mealy  
![[Mealyho automat]]
## Moore 
![[Mooreův automat]]