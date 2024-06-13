# AD převodníky
Typ
Rozsah vstupního napětí
Výstupní kód
Počet kanálů
Rychlost převodu
Chyby převodu

[[AD převod]]
## Chyby převodu
Chyba zesílení vstupního zesilovače
Chyba offsetu
Linearita převodníku
Drift teplotní, napěťový
Šum

Nehomogenita sensoru

## Typy
- Flash, half-flash
- Single slope (integrační)
- Succesive Approximation Register (SAR – Aproximační)
- Cyclic ADC
- Delta Sigma

### Integrační převodník
![[Signle-slope ADC.png]]

Nízký šum
Malá plocha
Počítáme čas do vyrovnání napětí

Rampa generována globálně
Komparátor
čítač
fosc >> framp

### Aproximační SAR převodník
![[Successive-approximation ADC.png]]
Metoda půlení intervalu
SAR = 011…1 ~  0.5 Vmax
Výstup komparátoru – první bit
Posuv SAR
N kroků pro N bitů

Nutný rychlý DAC:
- R-2R nelze vyrobit
- C-2C

![[C-2C.png]]

Rychlost, nízký šum, malá plocha

### Delta Sigma převodník
Integrace proudu PD
Komparace s 0
Q Vyrovnání vstupního proudu na 0
Měření času zapnuto/vypnuto

![[Delta-sigma ADC.png]]

### Cyklický ADC
![[Residue amplifier ADC.png]]

Aproximační algoritmický

SH uchová měřenou veličinu
Porovnání – uložení bitu -1/1
Residuální napětí přičteme nebo odečteme

Počet cyklů == přesnost

$V_{resout} = GV_{resin} - dV_{ref}$ 

## Triky převodů
Rozdílné kvantizační kroky
Nelineární rampa, přeskakování čítání
Gray, Johnson counter
Paralelismus