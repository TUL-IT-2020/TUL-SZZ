# Přenos dat

## VGA
![[VGA]]

## Sérioparalelní LVDS
![[Sérioparalelní LVDS]]

## MIPI
![[MIPI]]

## SPI, IIC
Pomalé sběrnice často součástí interface pro řízení

[[I2C|IIC]]
Až 5 Mbit/s – MIPI CSI, jinak ne

[[SPI|SPI]] - Serial Peripheral Interface 
Není specificky limitováno (100 MHz)
QSPI teoreticky 400 Mbit/s

## GiGE Vision
Sdružení výrobců pro standardizaci průmyslových rozhraní AIA.
Atmel, Basler, Teledyne DALSA, JAI, National Instruments, Stemmer..

Založené na IP protokolu

Řídící protokol UDP
- Seznam povinných registrových adres
- Volitelné prostory pro specifické nastavení
Stream protokol UDP
- Frame buffer na obou stranách
- Výpočet CRC
- Retransmit paketů
Mechanismus objevení zařízení

>[!note] 
>Kluci si na UDP naprogramovali vlastní TCP. Proč?

125MB/s, levná a dlouhá kabeláž CAT5e, stačí síťová karta.

## USB3 Vision
Definuje specifickou USB třídu (0xEF, 0x05). Mechanismy detekce, přístupu k registrům, streamování (GenICam).

USB3 zero copy vs USB2
na USB2 nelze provozovat nejen kvůli šířce pásma

USB 3.1 Gen1 (USB 3.2 Gen 1) – 5 Gbit/s
Kódování 8b/10b + overhead -> Až 480 MB/s
Micro B konektor
Kabeláž není vždy kompatibilní. Omezená délka připojení (5m). Omezený počet připojených zařízení.