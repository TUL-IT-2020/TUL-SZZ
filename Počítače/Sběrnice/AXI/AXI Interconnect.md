# AXI Interconnect
> [!example] Soubor IP jader sloužících vytvoření sběrnic v SoC
>- AXI Crossbar
>- AXI Data Width Converter
>- AXI Clock Converter
>- AXI Data FIFO
>- AXI Register Slice
>- AXI MMU

> [!tip] Interconnect
> V rámci Vivado je lze použít samostatně, ale častěji jsou použity v rámci jedné parametrizované instance „Interconnect“.

## AXI Crossbar
Optimalizace propojení
- Na rychlost
- Na plochu

Varianty
- N:1
- 1:N
- Crossbar N:M
- Shared N:M

### N:1
![[AXI Crossbar N-1.png]]
### 1:N
![[AXI Crossbar 1-N.png]]
### Crossbar N:M
![[AXI Crossbar N-M.png]]
### Shared N:M
![[AXI Shared N-M.png]]