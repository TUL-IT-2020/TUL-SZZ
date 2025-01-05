# AXI Uart lite
Full duplex asynchronní sériový point to point přenos dat bez řízení toku. Data i synchronizace přenášena po jednom vodiči (RX a TX). Bez handshake rychlosti – staticky nastavené pro syntézu.

HW Parametry:
- start bit: 1
- délka: 5-9
- parita: žádná, lichá, sudá
- stop bit: 1-2
- Rychlost <9600, 230400> baud (1963 Bell 103 – 300 baud)

8bit FIFO paměti o kapacitě 16 slov s možností resetu
Interrupt volitelně generován při změně FIFO empty → not empty

![[AXI Uart data.png]]
![[AXI Uart BD.png]]