## Testování
Privátní metody nelze snadno přímo testovat.

- Unit testy
Testování jednotlivých častí.

- Integrační testy
Simulace běhu aplikace.

### Black box testování
Testuji z venčí podle specifikace chování dané funkce, třídy. Nezajímá nás vnitřní struktura.
#### Limitní stavy
- min
- blízké min
- blízké nule
- nula
- blízké nule
- blízké max
- max

### White box testování
Musíme projít každou nezávislou cestu vývojového diagramu.
#### Třídy ekvivalence
- některé testy jsou ekvivalentní (nemusíme je dělat)
Příklad:
```C
if (x > 100 && x < 200)
```
třídy ekvivalence:
- -inf, 100
- 100, 200
- 200, +inf
V každé třídě testuji limitní stavy.

#### Testování if
#### Testování for
- n-1, n, n+1

• Testování cyklů
1. přeskoč cyklus,
2. pojdi právě jednou,
3. projdi dvakrát,
4. projdi m krát, m < n, kde n je max. počet
průchodů
5. projdi n-1, n , n+1 krát

### Moc třída
Simuluje chování něčeho k čemu nemám přístup, ale je součástí finálního sw.

### Extrémní programování
Nejprve se píší testy, poté až implementace
Unit testy pro specifikaci.


### TDD - test driven development
Test, implementace, iterace