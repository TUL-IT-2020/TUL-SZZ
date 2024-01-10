## Hazardy
#příklad

slajd: 57
Určete CPI proudově pracujícího procesoru, kde je dána četnost hazardů a způsobené pozastavení: 
- RAW hazardy nastanou v 10 % instrukcí, průměrné pozastavení 2 takty
- WAW hazardy nastanou v 0,5 % instrukcí, průměrné pozastavení 4 takty; 
- řídicí hazardy v důsledku provedených skoků nastanou v 9 % instrukcí, průměrné zdržení jsou 3 takty; 
- strukturní hazardy v důsledku nedostupné jednotky či registrového zápisového portu nastanou v 3 % instrukcí, průměrné zdržení jsou 2 takty. 

Vycházíme z předpokladu, že pro ideální proudově pracující procesor platí: CPI = 1 (1 instrukce za jeden strojový takt).

$CPI = 1 + 0,1*2 + 0,005*4 + 0,009*3 + 0,03*2 = 1,55$


slajd: 67
1)
$CPI = \frac{10}{6} = 1,66$
$S_K = \frac{4*6}{10} = 2,4$
$E_K = \frac{S_K}{K} = \frac{2,4}{4} = 0,6 => 60\%$

2)
$S_a = \frac{t}{\frac{t}{k.m} + t_d} = \frac{100}{\frac{100}{4*3} + 5} = 7,5$
$S_b = \frac{t*IPC}{\frac{t}{K}+t_d} = \frac{100*3}{\frac{100}{4}+5}=10$

slajd: 68
$$
S_K = \frac{1}{
	\frac{0,13}{6-4} +
	\frac{0,25}{6-1} +
	\frac{0,62}{6}
} = 4,58
$$
