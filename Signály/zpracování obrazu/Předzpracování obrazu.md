# Předzpracování obrazu
## Transformace jasu
![[Transformace jasu]]
## Histogram obrazu
![[Histogram obrazu]]

## Černý bod
Určení hranice, pro kterou považujeme bod za černý. Nastavení všech pixelů s menším jasem na 0. Pomocí úpravy histogramu.

## Vyvážení bílé
![[Vavýžení bílé.jpg]]

Co je bílá?
V RGB prostoru (255, 255, 255). Pro lidské oko může být hodnota jinde. Změna vnímání s teplotou osvětlení.

Přepočet prakticky:
1) Určíme bílou barvu na snímku. 
2) Korekce tak, aby její hodnota po přepočtu byla bílá. 
3) Upravíme ostatní barvy lin. interpolací.

## Filtrace obrazu
![[Filtrace obrazu]]