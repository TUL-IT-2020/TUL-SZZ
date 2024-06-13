# LIDAR
LIDAR – LIght Detection And Ranging

Mechanická konstrukce – otočný optický element.
Plošný nebo čárový sensor – snímán každý bod.
Vyžaduje čárový nebo plošný projektor. Většinou frekvence NIR+.
Získáno mračno bodů -> Softwarové vyhodnocení (typicky NN klasifikace).

Využití:
Archeologický průzkum, ADAS, robotika.

Problémy:
Vzájemné rušení více zařízení.
Nepočítá s pohybem objektu.

## LIDAR - skenování
![[LIDAR - skenování.png]]
Bodový
Single pixel
Kamera

Čárový
Řádková kamera
Plošná kamera

Flood
Koaxiální

## Triangulace
Kamera (řádková, plošná) a LASER (bodový, čárový laser)
úhel
Změna výšky snímaného objektu je promítnuta na snímač
px
rozměry a rozlišení snímače
3.5 μm, při 𝛼 =45, 1px = 3.5 μm

Střed čáry
Prahování + těžiště - nepřesné
LASER ~ Gauss => aproximace středu => zvýšení přesnosti (až 100x!)

Nutný rigidní systém a reference
Jako kompletní sensor: μ-epsilon optoNCDT, 0.03um, 50KHz

## LASER mikrometr
Postup:
1. Otočný zrcadlový oktagon + LASER LED => Generování průběžného paprsku.
2. Rozptylka => rovnoběžné paprsky.
3. Spojka => přivedení signálu na detektor.
4. Měření hodnoty průběhu signálu

Přesnost ovlivněna:
Rychlost, optika, vyhodnocení na výstupu
Průhledné objekty?

Nebo:
čárový difrakční element
řádková nebo plošná kamera