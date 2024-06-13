# Time of Flight
Měření vzdálenosti
Princip ToF:
1) Zdroj světla je na krátký okamžik sepnut.
2) Světlo se odrazí od měřeného objektu.
3) Odražené světlo dopadá na snímač.

Měříme čas mezi vysláním pulsu a jeho přijetím.

$c = 300\; 000\; 000\; m/s$ => rychlý čítač

## Problémy
Nízké rozlišení $[m]$, aliasing.
Okolní světlo -> Kalibrace na osvětlení pozadí.
Rušení -> Využití neběžného světla (IR LASER LED).
Materiál objektu

## Nepřímé ToF
### Pulsní metoda
Vyžaduje dva snímače. Snímání je fázově posunuto.
$$
t_{pulse}/2
$$
Měříme poměr náboje na senzorech.

### Průběžné okno
Měříme fázi pomocí 4 snímačů.

Redukuje chybu způsobenou okolním osvětlením.
Aliasing - 
Modulace frekvence a amplitudy pulsů, např.:
Stepped Frequency Continuous Wave, Amplitude Modulation CW

