# Střadačově orientovaná ISA
## Charakteristika
Střadač == akumulátor

> [!tip] Zdrojem a cílem většiny instrukcí je akumulátor.

| instrukce | operace                            |
| --------- | ---------------------------------- |
| INC       | adds 1 to Acc                      |
| ADD Rx    | Add Rx to Acc and stores it in Acc |
| LOAD 10   | Stores constant to Acc             |
Krátké instrukce ?= krátké programy

Intensivní přístup do paměti
Chybí registry

## Zástupci
4004, 8051, ..