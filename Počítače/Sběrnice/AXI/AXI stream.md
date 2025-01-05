# AXI Stream
Základ. Z pohledu ostatních se jedná o datový kanál.

Variabilní protokol:
- Neomezená délka dávky (burst)
- Změna dat
- Řazení, míchání…

![[AXI stream.png]]
## AXI-4 Stream - signály
![[AXI-4_signály.png]]
Povinné:
- CLK - hodiny
- TDATA - data

Nepovinné:
- ARESETn - negativní reset
- TVALID – Master je připraven
- TREADY – Slave je připraven
- … viz tabulka

Ekvivalent komunikace mezi dvojicí FIFO
- TVALID ≈ Master FIFO není prázdná
- TREADY ≈ Slave FIFO není plná

![[AXI-4_signaly_tabulka.png]]

## Transakce
Transakce nastává
Náběžná hrana CLK & TVALID == 1 & TREADY ==1

Master nastaví TVALID do 1
TVALID nesmí do 0, nastavil-li 1 a nebylo READY
Společně s TVALID připraví validní TDATA
Master nesmí vyčkávat na TREADY

Slave
Může přijmout transakci nastavením TREADY do 1
![[AXI-transakce.png]]![[AXI-VALID before READY.png]]
![[AXI - READY before VALID.png]]

## Back pressure

![[AXI - Back pressure.png]]

Problém pomalého pracovníka

> [!question] Co dělat když jeden na cestě nestíhá?
>- Control
>- Drop
>- Buffer

Problém kombinační cesty TREADY

FIFO nebo skid buffer (register slice)