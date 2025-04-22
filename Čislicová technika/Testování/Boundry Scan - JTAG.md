# Boundry Scan - JTAG
- IEEE 1149.1
- JTAG

Původně určeno ke skenování vstupů a výstupů.
Zapojuje smyčku na rozhraní všech dílčích obvodů. Tím je umožněno seriové skenování.

Piny:
- `TDI` - test data in
- `TDO` - test data out
- `TCK` - test clock
- `TMS` - test mode select
- `TRST` - test reset

Všechno to řídí `TAP` (test access port) controler.