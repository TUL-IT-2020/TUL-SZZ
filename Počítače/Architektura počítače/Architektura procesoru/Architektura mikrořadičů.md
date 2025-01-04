# Architektura mikrořadičů
Mikrořadič je jednoobvodový (jednočipový, monolitický) μP (mikroprocesor doplněný paměťmi a periferiemi). Vyznačují se velkou spolehlivostí a kompaktností, proto jsou určeny především pro jednoúčelové aplikace do vestavěných systémů.

![Blokové schéma mikrořadiče](TUL-SZZ/assets/počítače/26_mikroradic.png)
*Blokové schéma mikrořadiče*

- RISC architektura (převážně jednocyklové instrukce, vyšší taktovací frekvence - např. 12 až 40 MHz)
- omezený soubor instrukcí (35–130)
- datová sběrnice relativně malá (8, 16, max. 32 bitů)
- relativně nízká cena (cca od 40,- Kč)
- široký rozsah napájecího napětí (od 2.7 V do 6 V)
- technologie CMOS
- střadačová nebo registrová ISA (příp. kombinace)
- vstupy a výstupy organizovány do bran (nutno nastavit jako vstupní nebo výstupní)
- integrované speciální obvody (PWM, ADC či DAC převodníky, komparátory, komunikační sběrnice, radiče displeje atd.)
- specializovane obvody uvnitř (ČASOVAČE, WATCHDOG, REALTIMECLOCK, ŘADIČ PŘERUŠENÍ ...)

