# Speciální kamery

## UV snímače
CCD snímače
12~24μm
512^2, 1024^2, 2048^2
<10(0) +/-,   1100 nm>
~1 fps
Hamamatsu, Teledyne, Sony

CMOS snímače zvládají +/- 400nm a vyšší fps
Optika – laboratorní sklo (quartz)

## Multispektrální kamery
Problém – ostření a chromatická aberace.
Řádková kamera JAI-SWEEP+ 4000Q.
Hranol s optimalizovaným výbrusem.
4 × 4K snímače: R, G, B, NIR
10GBit fiber 

## RGB-NIR
Snímače Omnivision RGB-Ir
Od 1280 × 720 do 5MPix

RGB-IR OX05B
2.5K×2K @60FPS
R, G, B, IR@940nm (36%QE)
Global shutter
MIPI nebo DVP
1.2K$ retail

Nebayerovská maska
2 × 2 nebo 4 × 4 pattern
16 – 2B, 8G, 2R, 4Ir

## NIR a SWIR snímače
Rozsah 750-1800

Aplikace
Spektrální čára vody
průhlednost plastů
křemík je průhledný – polovodičový průmysl
měření teplot >250°C
nutné osvětlení

InGaAs sensory
Sony Framos (IMX990/991), 5μm, 0,3-1,34 Mpix
New Imaging Technologies, 15μm, 0,32 MPix

RTI International - Colodial Quantum Dot 
Vyrobeno na čistém CMOS
nižší cena, 0,3-2Mpix,  QE ~ 15%

## Infračervené kamery
Pásmo LWIR 8-14μm
Dle planckova zákona objekty samy vyzařují při běžných teplotách
Sklo působí jako překážka – Germaniové objektivy
Je mimo křemíkové pásmo

Aplikace
Noční vidění, inspekce elektroniky, bezpečnost, detekce materiálů

Citlivost
Nepoužívá se QE - Noise Equivalent Temperature Difference $[mK]$

## Bolometrické snímače
Bolometr
Je zařízení pro měření tepelného záření. Odpor závislý na teplotě – V2O5 (oxid vanadičný), amorfní křemík.

Microbolometer array (Focal Plane Array)
pole ~ CCD
vyčítací mechanismus
řádky, sloupce (zesilovače)
konstantní napětí na všech elementech
měří se proud – CTIA zesilovač

Výrobci:
- BAE, DRS, Raytheon
- FLIR, NEC, LYNRED(Fr)
Strategická součástka

## Chyby měření LWIR
Non Uniformity Correction
Vlivem nedokonalostí výroby je charakteristika bolometrů odlišná
Základní dvoubodová korekce offsetu a zesílení
Referenční zdroj záření – černé těleso

Chlazení
Starší a přesnější sensory se chladí
tekutý dusík, Stirlingův motor, Peltierův článek
Nechlazené sensory mohou časem driftovat
průběžná korekce offset (plocha homogenní teploty)

## Polarizační snímače
Řada Sony Polarsens
Polarizační filtry pod vrstvou čoček
4 filtry (0, 45, 90, 135°)
Poměrem úhlů a intenzity odrazu lze odstranit odrazy

Yang, F. et all; A Method of Removing Reflected Highlight on Images Based on Polarimetric Imaging, Journal of Sensors 2016

## Inteligentní kamery
Kamery opatřené elektronikou a vhodným SW pro zpracování obrazu. Typicky opatřena IO pro připojení k PLC. Dříve primitivní funkce (hledání hran, atp.).
Dnes vše myslitelné:
- automatické nastavení jasu a barev,
- fotogrammetrie,
- kolorimetrie,
- čtení a detekce čárových a QR kódů,
- OCR,
- Nějaká forma neuronových sítí.

Součástí je většinou SW k uživatelsky jednoduchému nastavení ($?).

Výrobci:
- Cognex, 
- Keyence, 
- Teledyne DALSA FLIR (Blackfly)