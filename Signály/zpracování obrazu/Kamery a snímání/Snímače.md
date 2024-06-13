# Snímače

## CCD
## CMOS
![[CMOS sensor.png]]

Sensor s pasivními pixely (PPS)
1 transistor na pixel. Malý pixel, může zabrat hodně plochy. Pomalý, nízký SNR.

Sensor s aktivními pixely (APS)
1.5-4 T na pixel. Rychlý, SNR-. Větší pixel, menší plocha (-). Aktuální stav.

Digitální sensor (DPS)
5+ T na pixel. Dobře technologicky škálovatelný. Rychlý, bez sloupcového šumu. Velký pixel, složitý na výrobu.

### Vlastnosti CMOS snímačů
Netrpí na blooming & smearing
Lze jednoduše získat celistvý snímek
QE dotáhla chlazené CCD
Násobně rychlejší než CCD
Levnější výrobní proces
Lze doplnit o ostatní obvodové prvky

CMOS dominuje v běžném a průmyslovém užití
CCD má lepší SNR, vědecké aplikace, NIR

### Povrchová úprava snímače
Mikročočky
Zaostřují světlo do fotosenzitivní části
Zvětšení vyplnění a citlivosti (i 2x)
Nejsou v ploše homogenní

Barevné filtry
Odstíní některé části spektra
Umožní barevné fotografie

## Barevný snímač
Foveon snímač
Využívá různé absorpce vlnových délek v hloubce sensoru.

Color Filter Array
Pravidelná propustná maska:
- Bayerovská, 
- Fuji X-trans, 
- Onsemi RGB-IR.
Nutné vypočítat ostatní barvy pro každý pixel. Problémy s moiré. Obtížná konverze do šedotónů.

Řádkové kamery
Multi nebo Hyperspektrální - rozklad hranolem / štěrbinou na plošný snímač. Více snímačů pro různé vlnové délky.

