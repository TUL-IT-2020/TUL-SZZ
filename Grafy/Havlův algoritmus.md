
> [!tip] Havlův algoritmus
Algoritmus který určí zda je zadaná posloupnost skórem některého jednoduchého grafu.

> [!info] Havlova redukce:
Jestliže $(d_1,d_2,...,d_n)$ je grafová posloupnost, potom $(d_2-1,...,d_{d_1+1}-1,d_{d1+2},...,d_n)$ je také grafová posloupnost (vynechali jsme jeden vrchol).

> [!info] Havlův algoritmus:
Opakujeme Havlovu redukci, po každé redukci posloupnost setřídíme nerostoucím způsobem, do doby než dostaneme posloupnost o které je zřejmé že je/není posloupnost některého grafu.

Ukončující podmínka:
- Posloupnost samých nul -> bylo to skóre nějakého grafu.
- Posloupnost obsahující záporné číslo -> není skóre žádného jednoduchého graf.

## Postup:
Grafová posloupnost: $(5,5,4,4,2,2)$
Počet vrcholů lichého stupně je sudý.

| odečtám: |     |     |     |     |     |
| -------- | --- | --- | --- | --- | --- |
| 5        | 5   | 4   | 4   | 2   | 2   |
| 4        | 3   | 3   | 1   | 1   |     |
| 2        | 2   |     |     |     |     |
| 1        | -1  |     |     |     |     |
Není graf.


Grafová posloupnost: $(5,4,4,3,3,2,1)$
Počet vrcholů lichého stupně je sudý.

| 5   | 4   | 4   | 3   | 3   | 2   | 1   |
| --- | --- | --- | --- | --- | --- | --- |
| 3   | 3   | 2   | 2   | 1   | 1   |     |
| 2   | 1   | 1   | 1   | 1   | 1   |     |
| 1   | 1   |     |     |     |     |     |
| 0   |     |     |     |     |     |     |
Je grafem.

 > [!note] Sestrojení grafu
 > Opačným postupe (přidáváním vrcholů) lze sestrojit graf s odpovídající posloupností.