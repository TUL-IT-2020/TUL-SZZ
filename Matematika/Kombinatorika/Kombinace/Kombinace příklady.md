# Kombinace

## Cvičení 1.3.1. 
V jisté loterii je každý týden taženo 6 různých čísel ze 49. Jaká je pravděpodobnost, že
ve dvou po sobě jdoucích týdnech budou tažena různá čísla?

### Postup
Kolik čísel máme na výběr druhý den?
49-6 = 43

Všechny možnosti:
$\binom{49}{6}$

Možnosti bez výskytu výběru prvního dne:
$\binom{43}{6}$

Pravděpodobnost:
$\binom{43}{6}/\binom{49}{6}$
### Řešení
$\binom{43}{6}/\binom{49}{6}= 0.436$

## Cvičení 1.3.2. 
V cukrárně prodávají 10 druhů zákusků. Kolika způsoby lze zakoupit 30 zákusků, jestliže od každého druhu chceme aspoň 2 zákusky?
### Postup

Počet pevně daných zákusků:
$2*10=20$

Počet zákusků k výběru:
$30-20=10$

Vybíráme:
- 10 zákusků z 10 druhů,
- nezávisí na pořadí,
- mohou se opakovat.

k = 10
n = 10
$\binom{n+k-1}{k}$

$C(10+10-1,10) = C(10+10-1,9)$ 

### Řešení
$C(19,9)=92378$