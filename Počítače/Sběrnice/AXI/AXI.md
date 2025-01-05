# AXI
> [!tip] AXI je rozhraní a protokol pro IP jádra
>- Symetrická – co má master má i slave
>- Pouze point-to-point (bez broadcast)
>- Master-Slave interface

> [!warning] Není to sběrnice
AXI popisuje rozhraní a protokol mezi master a slave.
Popisuje pouze propojení mezi jedním master a jedním slave.
Ale nějaké sběrnice obsahuje.

![[AXI interconnect.png]]

[[Termíny periferií]]
## AMBA 
Část specifikace ARM AMBA (od 3 výše)

AMBA : Advanced Microcontroller Bus Architecture
- Advanced Peripheral Bus
	- Pomalé periferie
- Advanced High-performance Bus
	- Rychlé periferie
- Advanced Extensible Interface
	- Rychlé i pomalé periferie

## AXI - 4

![[AXI-4.png]]

![[AXI-4_kategorie.png]]

### AXI stream
![[AXI stream]]

### AXI-4 Lite
![[AXI-4 Lite]]

### AXI-4 Memory Map
![[AXI-4 Memory Map]]
### AXI-4 Lite & MM
![[AXI-4 Lite & MM]]

### AXI Interconnect
![[AXI Interconnect]]
## AXI Central DMA
![[AXI Central DMA]]
## Periferie připojitelné na AXI

### AXI GPIO
![[AXI GPIO]]
### AXI Uartlite
![[AXI Uartlite]]

### AXI Quad SPI
![[AXI Quad SPI]]

### AXI IIC
![[AXI IIC]]

