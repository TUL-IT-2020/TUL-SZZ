# Klasifikace vs lokalizace vs detekce

- klasifikace: return 1
- lokalizace: return (1, x, y, w, h)
- detekce: `return [ (1, x1, y1, w1, h1), (1, x2, y2, w2, h2) ]`

## Klasifikace
![[Klasifikace]]

## Lokalizace
Kromě třídy bude síť zároveň predikovat pozici objektů ve formě obdélníků.
Problém transformován na úlohu klasifikace + regrese.

## Detekce
- Posuvné okénko (pomalé)
- R-CNN (nejdřív najdi zajímavý region -> klasifikace)
- Posuvné okno jako konvoluce (nejdřív konvoluce, pak výřez, pak klasifikace)
- YOLO