#příklad 
# Soustavy kongruencí prvního stupně
Aplikace Čínské věty o zbytku.
## Příklad
$x \equiv 3(5)$, 
- $b_1, m_1$
$x \equiv 6(7)$, 
- $b_2, m_2$
$x \equiv 5(9)$, 
- $b_3, m_3$
$x \equiv 2(11)$, 
- $b_4, m_4$

### Postup

$\forall i\neq j \;; NSD(m_i,m_j) = 1$
Po dvou nesoudělná.

$M = NSN(m_1,...,m_n)$
$M = 5*7*9*11 = 3 465$

| $M_i$ | 693 | 495 | 385 | 315 |
| ---- | ---- | ---- | ---- | ---- |
| $\bar{M_i}$ | 2 | 3 | 4 | 8 |
- $M_i = \frac{M}{m_i}$
- $M_i*\bar{M_i} \equiv 1 (m_i)$

$693\bar{M_1} \equiv 1 (5)$
$3\bar{M_1} \equiv 1 (5)$
$\bar{M_1} \equiv 2$

$495\bar{M_2} \equiv 1 (7)$
$5\bar{M_2} \equiv 1 (7)$
$\bar{M_2} \equiv 3$

$385\bar{M_3} \equiv 1 (9)$
$7\bar{M_3} \equiv 1 (9)$
$\bar{M_3} \equiv 4$

$315\bar{M_4} \equiv 1 (11)$
$7\bar{M_4} \equiv 1 (11)$
$\bar{M_4} \equiv 8$

$x \equiv M_1\bar{M_1}b_1 + ... + M_4\bar{M_4}b_4(M)$
$x \equiv 693*2*3 + 495*3*6 + 385*4*5 + 315*8*2(3 465)$
$x \equiv 25 808(3 465)$
$x \equiv 1553(3465)$
### Řešení
$x \equiv 1553(3465)$

## Příklad
$2x \equiv -6(15)$
$2x \equiv +3(9)$
$3x \equiv -9(10)$
$3x \equiv -15(8)$
### Postup
Převod do základního tvaru:
$2x \equiv -6(15)$
$2x \equiv 9(15)$
$9 = 2*y(15)$
$(15+9)/2 = 12$
$x \equiv 12(15)$

$2x \equiv +3(9)$
$(3+9)/2 = 6$
$x \equiv 6(9)$

$3x \equiv 1(10)$
$\frac{2*10+1}{3} = 7$
$x \equiv 7(10)$

$3x \equiv -15(8)$
$3x \equiv 1(8)$
$\frac{1+8}{3} = 3$
$x \equiv 3(8)$

Výpočet M:
$M=NSN(8,9,10,15) = 2^3 * 3^2 * 5 =360$

Tvorba tabulky:

| $m_i$ | 15 | 9 | 10 | 8 |
| ---- | ---- | ---- | ---- | ---- |
| $d_i$ | 1 | 9 | 5 | 8 |
| $c_i$ | 0 | 280 | 216 | 225 |
| $b_i$ | 12 | 6 | 7 | 3 |
- $d_i$ - po dvou nesoudělné
$$
c_i \equiv 0 \left(\frac{M_i}{d_i}\right) \wedge c_i \equiv 1 (d_i)
$$

$c_1 \equiv 0 \left(360\right) \wedge c_1 \equiv 1 (1)$
$c_2 \equiv 0 \left(40\right) \wedge c_2 \equiv 1 (9)$
$c_3 \equiv 0 \left(72\right) \wedge c_3 \equiv 1 (5)$
$c_4 \equiv 0 \left(45\right) \wedge c_4 \equiv 1 (8)$

$40t \equiv 1 (9)$
$4t \equiv 1 (9)$
t = 7
$7*40$

$72t \equiv 1 (5)$
$2t \equiv 1 (5)$
t = 3
$3*72$

Výsledná kongruence:
$$
x \equiv \sum_{i=1}^4 c_ib_i (M)
$$
$x\equiv 0*12+ 280*6 + 216*7 + 225*3(360) \equiv 267(360)$

### Řešení
$x \equiv 267(360)$

## Příklad

Nalezněte řešení soustavy kongruencí $x \equiv 3 (mod 11); x \equiv 2 (mod 8); x \equiv 5 (mod 9)$. Výsledek vyjádřete v soustavě nejmenších nezáporných zbytků vhodného modulu.
### Postup

$M = NSN(11,8,9) = 2^3*3^2*11 = 792$

72t = 3(11)
6t = 3(11)
t = 6

99t = 2(8)
3t = 2(8)
t = 6

88t = 5(9)
7t = 5(9)
t = 2

$x = 72*6 + 99*6 + 88*2 (792)=1202(792)=410(792)$
### Řešení
$x =410(792)$
# Obecné soustavy
## Příklad
Vyřešte soustavu kongruencí $x \equiv 2(6),x \equiv 4(14),x \equiv 5 (15), x \equiv 10(20)$. Výsledek zapište v soustavě nejmenších nezáporných zbytků vhodného modulu.

### Postup
Převod soustavy kongruencí na nesoudělné moduly:

| $x_i$ | $\equiv$ | $b_{old}$ | $(m_i)$ | - | rozklad modulu | $b_i$ | $(d_i)$ |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| x |  | 2 | (6) |  | 2*3 | 2 | (3) |
| x |  | 4 | (14) |  | 2*7 | 4 | (7) |
| x |  | 5 | (15) |  | 3*5 | 0 | (5) |
| x |  | 10 | (20) |  | 4*5 | 2 | (4) |
|  |  |  |  |  |  |  | 420 |
Výpočet nového modulu:
$M = NSN(6,14,15,20) = 2^2*3*5*7 = 420$

Získání $c_i$:
$M/d_i * c_i = b_i(d_i)$

$140 c_1 \equiv 2(3)$
$2 c_1 \equiv 2(3)$
$c_1 = 1$

$60 c_2 \equiv 4(7)$
$4 c_2 \equiv 4(7)$
$c_2 = 1$

$84 c_3 \equiv 0(5)$
$4 c_3 \equiv 0(5)$
$c_3 = 0$

$105 c_4 \equiv 2(4)$
$1 c_4 \equiv 2(4)$
$c_4 = 2$

Výpočet výsledné kongruence:
$x \equiv \sum^4_{i=1} M/d_i*c_i (M)$
$x = 140*1 + 60*1 + 84*0 + 105*2(420) = 410(420)$
### Řešení
$x = 410(420)$

## Příklad
Uvažujte soustavu kongruencí $x \equiv 2 (10), x \equiv 4 (12), x \equiv 7(15),x \equiv 7 (9)$. 
1) Nalezněte všechna celá čísla, která ji vyhovují. 
2) Rozhodněte, zda existuje celé číslo větší než `92 222`, které vyhovuje dané soustavě. V kladném případě určete nejmenší takové číslo. Vždy používejte soustavu nejmenších nezáporných zbytků.
### Postup
Převod soustavy kongruencí na nesoudělné moduly:

| $x_i$ | $\equiv$ | $b_{old}$ | $(m_i)$ | - | rozklad modulu | $b_i$ | $(d_i)$ |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| x |  | 2 | (10) |  | 2*5 | 0 | (1) |
| x |  | 4 | (12) |  | 3*4 | 0 | (4) |
| x |  | 7 | (15) |  | 3*5 | 2 | (5) |
| x |  | 7 | (9) |  | 3*3 | 7 | (9) |
|  |  |  |  |  |  |  | 180 |
Výpočet nového modulu:
$M = NSN(10,12,15,9) = 2^2*3^2*5 = 180$

$M/d_i * c_i = b_i(d_i)$

$180c_1 = 0(1)$
$c_1 = 0$

$45c_2 = 0(4)$
$c_2= 0$

$36c_3= 2(5)$
$c_3 = 2$

$20c_4= 7(9)$
$2c_4 = 7(9)$
$c_4 = 8$

Výpočet výsledné kongruence:
$x \equiv \sum^4_{i=1} M/d_i*c_i (M)$
$x = 180*0 + 45*0 + 36*2 + 20*8 (180)= 232(180)=52(180)$

Větší než `92 222`:
$92 222 \equiv 62 (180)$
$62-52 = 10$
$x = 92 222 + 180 - 10 = 92392$
### Řešení
1) $x \equiv 52 (180)$
2) Existuje jich nekonečně mnoho v rozestupu 180.
Nejmenší takové číslo je: $x = 92392$

## Příklad
Nalezněte řešení následující soustavy kongruencí $x \equiv 9 (84), x \equiv 3 (90), x \equiv 18 (165)$.
### Postup
Převod soustavy kongruencí na nesoudělné moduly:

| $x_i$ | $\equiv$ | $b_{old}$ | $(m_i)$ | - | rozklad modulu | $b_i$ | $(d_i)$ |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| x |  | 9 | (84) |  | $2^2*3*7$ | 9 | $(2^2*7)$ |
| x |  | 3 | (90) |  | $2*3^2*5$ | 3 | $(3^2*5)$ |
| x |  | 18 | (165) |  | $3*5*11$ | 7 | $(11)$ |
|  |  |  |  |  |  |  | $13 860$ |
Výpočet nového modulu:
$M = NSN(84,90,165) = 2^2*3^2*5*7*11 = 13 860$

495t = 9(28)
19t = 9(28)
t = 27

308t = 3(45)
38t = 3(45)
t = 6

1260t = 7(11)
6t = 7(11)
t = 3

$x = 495*27 + 308*6 + 1260*3 (13860) =18993(13860)=5133(13860)$
### Řešení
$x = 5133(13860)$

## Příklad
Vyřešte soustavu kongruencí $22x \equiv 84 (15), 16x \equiv 42 (9), 17x \equiv 49 (10), 15x \equiv 21 (8)$. Výsledek zapište v soustavě nejmenších nezáporných zbytků odpovídajícího modulu.
### Postup
Úprava kongruencí do základního tvaru:
- $22x \equiv 84 (15)$,
- 7x = 9(15)
- x = 12(15)

- $16x \equiv 42 (9)$,
- 7x = 6(9)
- x = 6(9)

- $17x \equiv 49 (10)$,
- 7x = 9(10)
- x = 7(10)

- $15x \equiv 21 (8)$.
- 7x = 5(8)
- x = 3(8)

Převod soustavy kongruencí na nesoudělné moduly:

| $x_i$ | $\equiv$ | $b_{old}$ | $(m_i)$ | - | rozklad modulu | $b_i$ | $(d_i)$ |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| x |  | 12 | (15) |  | 3*5 | 0 | (1) |
| x |  | 6 | (9) |  | 3^2 | 6 | (3^2) |
| x |  | 7 | (10) |  | 2*5 | 2 | (5) |
| x |  | 3 | (8) |  | 2^3 | 3 | (2^3) |
|  |  |  |  |  |  |  | 360 |
Výpočet nového modulu:
$M = NSN(15,9,10,8) = 2^3*3^2*5 = 360$

40t= 6(9)
t = 6

72t= 2(5)
t = 1

45t= 3(8)
t = 7

$x =40*6 + 72*1 + 45*7 (360) = 627(360)=267(360)$
### Řešení
$x = 267(360)$