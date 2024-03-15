## Vzorové návrhy na Xilinq FPGA
### Prorietární kód pro daná model Xilinq
IP jádra
Project manager -> IP catalog
bram
Block Memory Generator

Init file:
Přípona: .coe
Umožnuje nahrát inicializaci do ROM/RAM.

### Přenositelnost vrámci Xilinq FPGA
Language template :
(tohle je ta podstatná knihovna)
RAM, BlockRAM, Dual Port, 1Clock, Write First mode

Nebo:
XPM - Xiling parametrized macros
(IP generátor pro nás dovede předvyplnit)