# AXI GPIO
Přímé ovládání vstupů a výstupů
Základem je třístavový budič IOBUF

HW volby:
- Počet kanálů
- Šířka kanálů
- Směr (IO, I, O)
- Povolení přerušení

Ovládací registry jsou přímo připojené k IOBUF
- 0x0 – Data 0
- 0x4 – TRI 0
- 0x8 – Data 1
- 0xC – TRI 1
- … interrupt 

![[AXI GPIO.png]]