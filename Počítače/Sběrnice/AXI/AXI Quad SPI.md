# AXI Quad SPI

- [[SPI]]

Podporováno / konfigurovatelné:
Režim XIP, Performance, Lite (připojení na sběrnici)
Módy:
- Single, 
- Dual, 
- Quad
Délka transakce 8, 16, 32
Samostatný hodinový vstup pro SPI:
- SCK=(SPI_CLK/(2,4,8,16))\*M<1,128>
- M pouze pro /16
Počet Slave v multidrop režimu
Master / Slave režim
Přerušení na příjem byte / dokončení transakce
RX a TX FIFO na  – 0, 16, 256

Podpora bootování FPGA


![[AXI Quad SPI.png]]