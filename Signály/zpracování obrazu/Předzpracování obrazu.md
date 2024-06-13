# Předzpracování obrazu
## Transformace jasu
![[Transformace jasu]]
## Histogram obrazu
Graf četnost zastoupení hodnot.
u čb – x = intenzita hodnto pixelů
u barevných histogramy kanálů

![[Histogram.png]]

Vyvážení histogramu
Roztáhnutí četnosti do používaného rozsahu.
Vypočítání distribuční funkce (Cummulative Distribution Function).
Normalizace CDF do intervalu 0-MAX (255).

Obraz s vyváženým histogramem nepřinese nové informace.

## Vyvážení histogramu barevného obrazu
> [!warning]
>Vyvážení R, G, B kanálů zvlášť nepřinese dobrý výsledek!
> Posun tónu změní vyznění obrazu.

Postup:
1) Převod do [[Barevné prostory a modely#YUV, Y’UV, YIQ|YUV]].
2) Vyvážení jasové složky
3) Převod do RGB

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