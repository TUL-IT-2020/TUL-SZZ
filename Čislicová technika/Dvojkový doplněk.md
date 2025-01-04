# Vlastnosti dvojkového doplňku
Řeší problém dvou nul

![[Dvojkovy_doplnek.png]]
## Počítáme ve dvojkovém doplňku
### Sčítání
Nevyžaduje speciální hardware (prostá sčítačka)
Problém rozsahu, overflow:
- Sečtěme dvě 4bitová čísla -2 + -2 = -4
- Sečtěme jiná dvě -7 + -7 = 2
Řešení – správný počet bitů

### Násobení
Rozsah: Nbit\*Mbit = (N+M)bit