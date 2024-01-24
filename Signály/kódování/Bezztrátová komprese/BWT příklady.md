#příklad
# BWT příklady
## Příklad komprese
Zakódujte zprávu: `ANANAS`. 
### Postup
1) blok o délce N (např. ANANAS), N cyklických posuvů o jeden symbol doprava
==> matice N * N, řádky => cyklické posuny
2) lexikografické (podle abecedy) setřídění matice
3) poslední sloupec je výsledek transformace
ANANAS
SANANA
ASANAN
NASANA
ANASAN
NANASA
==>
ANANAS
ANASAN
ASANAN
NANASA
NASANA
SANANA
4) přidáme číslo řádku v setříděné matici, kde se nachází vstupní řetězec: **SNNAAA, 1. ŘÁDEK**

### Řešení
Zakódováno na **SNNAAA**.

## Příklad dekódování
Zakodovano: SNNAAA, 1. ŘÁDEK

### Postup
|1|sort|2|sort|3|sort|4|sort|5|sort|6|sort|
|---|---|---|---|---|---|---|---|---|---|---|---|
|S|A|SA|AN|SAN|ANA|SANA|ANAN|SANAN|ANANA|SANANA|ANANAS|
|N|A|NA|AN|NAN|ANA|NANA|ANAS|NANAS|ANASA|NANASA|ANASAN|
|N|A|NA|AS|NAS|ASA|NASA|ASAN|NASAN|ASANA|NASANA|ASANAN|
|A|N|AN|NA|ANA|NAN|ANAN|NANA|ANANA|NANAS|ANANA|SNANASA|
|A|N|AN|NA|ANA|NAS|ANAS|NASA|ANASA|NASAN|ANASAN|NASANA|
|A|S|AS|SA|ASA|SAN|ASAN|SANA|ASANA|SANAN|ASANAN|SANANA|

### Řešení
VÝSTUP: ANANAS