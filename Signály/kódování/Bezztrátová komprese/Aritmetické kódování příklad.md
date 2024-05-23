#příklad
# Aritmetické kódování

## Příklad komprese
Datový řetězec: `CBAABCADAC` (10 znaků)
1) Pravděpodobnosti výskytu A – 0.4 (P1), B – 0.2 (P2), C – 0.3 (P3), D – 0.1 (P4)
2) rozdělení v intervalu <0, 1):
<0, P1), <P1, P1 + P2), <P1 + P2, P1 + P2 + P3), <P1 + P2 + P3, P1 + P2 + P3 +P4)
Kumulativní pravděpodobnosti:
Q0 = 0, Q1= P1, Q2 = P1 + P2, … ,QN = P1 + P2 + … + PN = 1

|<0, Q1)| <Q1, Q2)| <Q2, Q3)| <Q3, Q4)|
|---|---|---|---|
|<0, 0.4)| <0.4, 0.6)| <0.6, 0.9)| <0.9, 1)|
|A | B | C | D |
3) Kódování:
==> postupné omezování intervalu I = <0, 1), I = <L, H)
==> Postupně jsou brány znaky z datového řetězce, k nim známe IZ = <ZL, ZH)
==> Nová hodnota intervalu IN = <L + ZL*(H - L), L + ZH*(H - L))
C ==> I = <0, 1), IN = <0 + 0.6*(1 – 0), 0 + 0.9*(1 - 0)) = <0.6, 0.9)
B ==> I = <0.6, 0.9), IN = <0.6 + 0.4*(0.9 – 0.6), 0.6 + 0.6*(0.9 – 0.6)) = <0.72, 0,78)
A ==> I = <0.72, 0.78), IN = <0.72 + 0*(0.78 – 0.72), 0.72 + 0.4*(0.78 – 0.72)) = <0.72, 0,744)
A ==> I = <0.72, 0.744), IN = <0.72 + 0*(0.744 – 0.72), 0.72 + 0.4*(0.744 – 0.72)) = <0.72, 0,7296)
B ==> I = <0.72, 0.7296), IN = <0.72 + 0.4*(0.7296 – 0.72), 0.72 + 0.6*(0.7296 – 0.72)) = <0.72384, 0.72576)
….
….
B ==> I = <0.72519936, 0.725208576), IN = <0.7252048896, 0.7252076544), C = 0.725205

## Příklad dekomprese
Výsledek kódování ==> C = 0.725205
1) Počáteční hodnota intervalu dekódování I = <0, 1)
2) dekódování znaku: K = ((C – L) / (H – L)); ZL <= K < ZH ==> nalezneme
odpovídající znak
3) počítáme nový interval IN = <L + ZL*(H - L), L + ZH*(H - L))
I = <0, 1), K = 0.725205, znak = C, IN = <0 + 0.6*(1 – 0), 0 + 0.9*(1 – 0) = <0.6, 0.9)
I = <0.6, 0.9), K = 0.41735, znak = B, IN = <0.6 + 0.4*(0.9 – 0.6),0.6 + 0.6*(0.9 – 0.6)) =<0.72, 0.78)
I = <0.72, 0.78), K = 0.08675, znak = A, IN = <0.72, 0.744)
I = <0.72, 0.744), K = 0.216875, znak = A, IN = <0.72, 0.7296)
….

## Příklad od Severýna

Je dána zdrojová abeceda A,B,C,D. 
Pravděpodobnosti výskytu jednotlivých znaků jsou: p(A) = 0.4, p(B) = 0.3, p(C) = 0.2 a p(D) = 0.1.  
Zakódujte zprávu ADCB aritmetickým kódováním.  

Jaká je minimální a maximální délka zprávy než bude dosaženo strojové přesnosti typu float (IEE754, 32-bit)?

### Postup
| Abeceda        | počátek | A   | B   | C   | D   |
| -------------- | ------- | --- | --- | --- | --- |
| Pravděpodbnost | 0       | 0.4    | 0.3    | 0.2    | 0.1    |
| Počátek kumulativni    | x        | 0    | 0.4    | 0.7    | 0.9    |
- $\alpha_j$ - počátek intervalu
- $l_j$ - šířka intervalu

Výpočet dalšího $\alpha$:
$\alpha_{n+1} = \alpha_n + l_n * \sum{p_k}$

- $P$ - pravděpodobnosti srovnané od nejvyšší
- $\sum_{i=0}^{k}{P_i}$ - kumulativní pravděpodobnost
	- $k$ - index pro kódovaný znak

Výpočet dalšího $l$:
$l_{n+1} = l_n * P_k$

- $P_k$ - pravděpodobnost daného znaku

| znak | $\alpha_j$ | $l_j$ | výpočet | výpočet |
| ---- | ---- | ---- | ---- | ---- |
| / | 0 | 1 |  |  |
| A | 0 | 0.4 | 0+0 | 1*0.4 |
| D | 0.36 | 0.04 | 0 + 0.4*0.9 | 0.4*0.1 |
| C | 0.388 | 0.008 | 0.36 +0.04*0.7  | 0.04*0.2 |
| B | 0.3912 |  | 0.388 + 0.008*0.4 | 0.008*0.3 |
### Řešení
Interval (0.3912, 0.3936)  
Minimální délka 7 znaků (samá 'D') - dosáhneme délky intervalů okolo 10^-7, což je strojová přesnost 32-bitového float-u.  
Maximální délka 17 znaků (samá 'A') - 0.4^17 = 1.72*10^-7

## Příklad

Je dána zdrojová abeceda A,B,C,D,E. 
Pravděpodobnosti výskytu jednotlivých znaků jsou: p(A) =  p(B) = p(C) = p(D) = p(E) = 0.2. 

Aritmetickým kódováním byla zakódována zpráva o délce čtyři znaky. Zpráva po zakódování je číslo 0.385.  
Jaká je nezakódovaná zpráva?

### Postup

| Abeceda | počátek | A | B | C | D | E |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| Pravděpodbnost | 0 | 0.2 | 0.2 | 0.2 | 0.2 | 0.2 |
| Počátek kumulativni | x | 0 | 0.2 | 0.4 | 0.6 | 0.8 |
$R = 0.385$

| $\alpha_j$ | $l_j$ | $\frac{R-\alpha_j}{l_j}$ | znak | výpočet |
| ---- | ---- | ---- | ---- | ---- |
| 0 | 1 | 0.385 | B | 0.385 < 0.4 |
| 0.2 | 0.2 | 0.925 | E | 0.925 < 1 |
| 0.36 | 0.04 | 0.625 | D | 0.625 < 0.8  |
| 0.384 | 0.008 | 0.125 | A | 0.125 < 0.2 |
Dekódovali jsme 4 znaky, algoritmus končí.
### Řešení
BEDA

## Příklad Koucký
Pomocí DFWLD:
- zakódujte: `dcae`
- dekódujte: `01100011`, 4 znaky

| Abeceda | počátek | a | b | c | d | e | f |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| Pravděpodbnost | 0 | 0.25 | 0.25 | 0.2 | 0.1 | 0.1 | 0.1 |
| Počátek kumulativni | x | 0 | 0.25 | 0.5 | 0.7 | 0.8 | 0.9 |
### Postup
Zakódování:

| znak | $\alpha_j$ | $l_j$ | výpočet | výpočet |
| ---- | ---- | ---- | ---- | ---- |
| / | 0 | 1 |  |  |
| d | 0.7 | 0.1 | 0+1*0.7 | 1*0.1 |
| c | 0.75 | 0.02 | 0.7+0.1*0.5 | 0.1*0.2 |
| a | 0.75 | 0.005 | 0.75+0.1*0.02 | 0.02*0.25 |
| e | 0.754 | 0.0005 | 0.75+0.8*0.005 | 0.005*0.1 |
Interval: <0.754,0.7545)
$R = \frac{s}{2^t}$
- $\frac{1}{2^t} < 0.0005 < \frac{1}{2^{t-1}}$
- $t = 11$
- $2^t = 2048$

$0.754*2048 = 1544.192$
$0.7545*2048 = 1545.216$

$R = \frac{1545}{2048}=(.110 0000 1001)_2$

Dekódování:
$(.0110 0011)_2$
$R= \frac{99}{2^8} = \frac{99}{256} \approx 0.3867$

| $\alpha_j$ | $l_j$ | $\frac{R-\alpha_j}{l_j}$ | výpočet | znak |
| ---- | ---- | ---- | ---- | ---- |
| 0 | 1 | 0.38 | 0.38 < 0.5 | b |
| 0.25 | 0.25 | 0.54 | 0.54 < 0.7 | c |
| 0.375 | 0.05 | 0.23 | 0.23 < 0.25 | a |
| 0.375 | 0.0125 | 0.93 | 0.93 < 1 | f |
### Řešení
Zakódováno na: $(.110 0000 1001)_2$
Dekódováno na: `bcaf`

## Příklad zakódování
Uvažujte zdrojovou abecedu:

| znak | a | b | c | d | e |
| ---- | ---- | ---- | ---- | ---- | ---- |
| četnost | 0,3 | 0,25 | 0,2 | 0,15 | 0,1 |

Metodou aritmetického kódování DFWLD zakódujte slovo `dccd`.
### Postup
| znak | a | b | c | d | e |
| ---- | ---- | ---- | ---- | ---- | ---- |
| četnost | 0,3 | 0,25 | 0,2 | 0,15 | 0,1 |
| kumulat | 0 | 0,3 | 0,55 | 0,75 | 0,9 |

| znak | $\alpha_j$ | $l_j$ | výpočet | výpočet |
| ---- | ---- | ---- | ---- | ---- |
| / | 0 | 1 |  |  |
| d | 0,75 | 0,15 | 0+1*0,75 | 1*0,15 |
| c | 0,8325 | 0,03 | 0,75+0,15*0,55 | 0,15*0,2 |
| c | 0,849 | 0,006 | 0,8325+0,03*0,55 | 0,03*0,2 |
| d | 0,8535 | 0,0009 | 0,849+0,006*0,75 | 0,006*0,15 |

Reprezentant: $R \in <0,8535;0,8544)$

$0,0009*2048>1$
$0,8535*2048 = 1747,9$ 
$0,8544*2048 = 1749,8$ 

$R = \frac{1748}{2^{11}} = \frac{437}{2^{9}} = (,1 1011 0101)_B$

$437_D = 256 + 128 + 32 + 16 + 4 + 1 = 1 1011 0101_B$
### Řešení
$R = \frac{437}{2^{9}}=(,1 1011 0101)_B$

## Příklad dekódování
Uvažujte zdrojovou abecedu:

| znak |a|b|c|d|e|
|------|-|-|-|-|-|
|četnost|0,35 | 0,3 | 0,2 | 0,1 | 0,05|

Dekódujte text `0111000001`, který vzniknul zakódováním 4 znaků metodou DFWLD.

### Postup
$0,0111000001_B = 1 1100 0001_B = 256 + 128+64+1 = 449$
$2^{10} = 1024$

$R = \frac{449}{1024} = 0,438 476 562$

| znak | a | b | c | d | e |
| ---- | ---- | ---- | ---- | ---- | ---- |
| četnost | 0,35 | 0,3 | 0,2 | 0,1 | 0,05 |
| kumulat | 0 | 0,35 | 0,65 | 0,85 | 0,95 |
Dekódování:

| $\alpha_j$ | $l_j$ | $\frac{R-\alpha_j}{l_j}$ | znak |
| ---- | ---- | ---- | ---- |
| 0 | 1 | 0,43>0,35 | b |
| 0,35 | 0,3 | 0,29>0 | a |
| 0,35 | 0,105 | 0,838>0,65 | c |
| 0,41825 | 0,021 | 0,96>0,95 | e |
### Řešení
Dekódovaná zpráva je `bace`.