# AXI Central DMA
Koprocesor přenosů dat 

![[AXI CDMA.png]]

Dílčí bloky:
- Datamover – přenos dat
- Řiditelné přímo pomocí AXI4-Lite

## Datamover – přenos dat
32-256bit sběrnice
Dávka 2-256 slov
Volitelně modul zarovnání dat
Volitelně Store&Forward FIFO

## Řiditelné přímo pomocí AXI4-Lite
CR/SR/SA/DA/BTT
Přenos zahájen zápisem do BTT

## Scatter Gather
Volitelně je možno přidat Scatter Gather 

Další AXI4-Master

Mikrokód přenosů v adresovatelné paměti
- transfer descriptor chain
- Struktura deskriptoru v tabulce →

Registry CURDES a TAILDES
Možno zapnout cyklické opakování. Poslední ukazuje na první.

> [!info] Proč?
V bare metal nemá smysl
Má smysl u OS s ochranou paměti:
>- Spojité paměti v Linux jsou problém
>- Segmentovaná data, stránkování paměti

| Transfer descriptor (32bit) | popis                        |
| --------------------------- | ---------------------------- |
| NXTDESC_PTR                 | Ukazatel na další descriptor |
| NXTDESC_PTR_MSB             | MSB ukazatele (64b addresa)  |
| SA                          | Zdroj kopírování             |
| SA_MSB                      | MSB zdroje (64b)             |
| DA                          | Cíl kopírování               |
| DA_MSB                      | MSB cíle (64b)               |
| CONTROL                     | Počet bajtů na přenos (25b)  |
| STATUS                      | Stav přenosu                 |