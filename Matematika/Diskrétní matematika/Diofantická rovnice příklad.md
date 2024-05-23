#příklad
# Diofantická rovnice
Na N nebo Z.
$ax+by = c$
- $a,b,c \in Z$

Existence řešení: $NSD(a,b)|c$
Počet řešení: 0 nebo $\infty$

$$
(x,y) = \left(x_p+y_p \right)+\left(x_h+y_h \right)
$$
Partikulární + obecné řešení

Využití [[Bézoutova rovnost příklad|Bezoutovy rovnice]].
Hledání partikulárního řešení:
$ax+by=c \;/NSD(a,b)$
$a_1x+b_1y=c_1$

Jo tak zbytku poznámek nerozumím už vůbec.
## Příklad
$$65366x+29348y=10672$$
Diofantická rovnice: $ax+by=c$
- a = 65366
- b = 29348
- $NSD(a,b)|c$ ?
### Postup

|  | = |  | x | $q_i$ | + | $r_i$ |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| 65366 |  | 29348 |  | 2 |  | 6670 |
| 29348 |  | 6670 |  | 4 |  | 2668 |
| 6670 |  | 2668 |  | 2 |  | 1334 |
| 2668 |  | 1334 |  | 2 |  | 0 |
$NSD(a,b) = 1334$
- $NSD(a,b)|c$ $\checkmark$ 

Rovnice po vykrácení s NSD:
$49x+22y=8$

|  | = |  | x | $q_i$ | + | $r_i$ |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| 49 |  | 22 |  | 2 |  | 5 |
| 22 |  | 5 |  | 4 |  | 2 |
| 5 |  | 2 |  | 2 |  | 1 |
| 2 |  | 1 |  | 2 |  | 0 |
Všimněte si že $q_i$ vychází stejně v obou tabulkách!

| i | -1 | 0 | 1 | 2 | 3 |
| ---- | ---- | ---- | ---- | ---- | ---- |
| $q_i$ | / | 2 | 4 | 2 | 2 |
| $P_i$ | 1 | 2 | 9 | 20 | 49 |
| $Q_i$ | 0 | 1 | 4 | 9 | 22 |
Použijeme dva poslední sloupečky křížem:
$NSD(49,22) = 1 = 49*9 + 22(-20)$

Jenže jsme chtěli: 8
$8 = 8*49*9 + 8*22(-20) = 49*72 + 22(-160)$

Partikulární řešení:
$x_0 = 72$ 
$y_0 = -160$

Homogenní řešení: 
$49(x) + 22(y)=0$
$x^h = \frac{-22}{49} y^h = -22\frac{y^h}{49}$ 
$y^h = 49*t$, $t \in Z$
$x^h = -22t$

### Řešení
$(x,y)=(72,-160) + (-22,49)t$
- $t \in Z$

## Příklad
$$54 740x - 38 157y= 1449$$
### Postup
|  | = |  | x | $q_i$ | + | $r_i$ |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| 54 740 |  | 38 157 |  | 1 |  | 16 583 |
| 38 157 |  | 16 583 |  | 2 |  | 4 991 |
| 16 583 |  | 4 991 |  | 3 |  | 1 610 |
| 4 991 |  | 1 610 |  | 3 |  | 161 |
| 1 610 |  | 161 |  | 10 |  | 0 |
$NSD(a,b) = 161$
- $54 740 / 161 = 340$
- $38 157 / 161 = 237$
- $1449 / 161 =9$

ANO má smysl pokračovat.
Po zkrácení:
$340x - 237y= 9$

| i | -1 | 0 | 1 | 2 | 3 | 4 |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| $q_i$ | / | 1 | 2 | 3 | 3 | 10 |
| $P_i$ | 1 | 1 | 3 | 10 | 33 | 340 |
| $Q_i$ | 0 | 1 | 2 | 7 | 23 | 237 |
Doplníme křížem:
$NSD(340,237) = 1 = 340(-23)-237(33)$

Partikulární řešení:
$9 = 340(-207)-237(297)$

Homogenní řešení:
$0 = 340(x)-237(y)$

$x_h = 237\frac{y_h}{340}$
$y_h = 340t$
$x_h=237t$
### Řešení
$(x,y) = (-207, 297) + (237, 390)t$
- $t \in Z$




## Příklad
$$26x + 46y = 10$$
Nalezněte všechna celočíselná řešení diofantické rovnice. Dále nalezněte řešení s vlastností, že $y$ je největší celé číslo menší než -100.
### Postup
Vyjádřete $NSD(a, b)$ ve tvaru $ax_0 + by_0$.

| dělenec | = | dělitel | * | $q_i$ | + | $r_i$ |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| 46 |  | 26 |  | 1 |  | 20 |
| 26 |  | 20 |  | 1 |  | 6 |
| 20 |  | 6 |  | 3 |  | 2 |
| 6 |  | 2 |  | 3 |  | 0 |

$NSD(a,b) = 2$
$2|c$
$13x + 23y = 5$

| i | -1 | 0 | 1 | 2 | 3 |
| ---- | ---- | ---- | ---- | ---- | ---- |
| $q_i$ | / | 1 | 1 | 3 | 3 |
| $P_i$ | 1 | 1 | 2 | 7 | 23 |
| $Q_i$ | 0 | 1 | 1 | 4 | 13 |
$13*(-7) + 23*(4) = 1$

Partikulární řešení:
$5 = 3*(-7*5) + 23*(4*5)$

Homogenní řešení:
$13x+23y = 0$

$x = -23 \frac{y}{13}$

$y = 13t$
$x = -23t$
$t \in Z$

### Řešení
$(x,y) = (-35, 20) + (-23t, 13t)$
$t \in Z$
## Příklad
Uvažujte diofantickou rovnici:
$$19x + 8y = 7$$
1) Nalezněte všechna řešení v oboru celých čísel, 
2) Nalezněte řešení, kde $x$ je nejmenší kladné přirozené číslo.
### Postup
| dělenec | = | dělitel | * | $q_i$ | + | $r_i$ |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| 19 |  | 8 |  | 2 |  | 3 |
| 8 |  | 3 |  | 2 |  | 2 |
| 3 |  | 2 |  | 1 |  | 1 |
| 2 |  | 1 |  | 2 |  | 0 |
$NSD(a,b) |c?$

| i | -1 | 0 | 1 | 2 | 3 |
| ---- | ---- | ---- | ---- | ---- | ---- |
| $q_i$ | / | 2 | 2 | 1 | 2 |
| $P_i$ | 1 | 2 | 5 | 7 | 19 |
| $Q_i$ | 0 | 1 | 2 | 3 | 8 |
$NSD(a,b) = 1 = 19(3) + 8(-7)$

Partikulární řešení:
$7 = 19(21) + 8(-49)$
Homogenní řešení:
$0 = 19x + 8y$

x = -8t
y = 19t
### Řešení
$(x,y) = (21, -49) + (-8t, 19t)$
$t \in Z$

## Příklad
Nechť:
- $a = 1398$,
- $b = - 612$. 
1) Nalezněte všechna celočíselná řešení rovnice $ax + by = 0$,
2) Nalezněte všechna celočíselná řešení rovnice $ax + by = -354$.

### Postup
| dělenec | = | dělitel | * | $q_i$ | + | $r_i$ |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| 1398 |  | 612 |  | 2 |  | 174 |
| 612 |  | 174 |  | 3 |  | 90 |
| 174 |  | 90 |  | 1 |  | 84 |
| 90 |  | 84 |  | 1 |  | 6 |
| 84 |  | 6 |  | 14 |  | 0 |
$NSD(a,b) |c?$
- 1398/6 = 233
- -612/6 = -102
- -354/6 = -59

| i | -1 | 0 | 1 | 2 | 3 | 4 |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| $q_i$ | / | 2 | 3 | 1 | 1 | 14 |
| $P_i$ | 1 | 2 | 7 | 9 | 16 | 233 |
| $Q_i$ | 0 | 1 | 3 | 4 | 7 | 102 |
$-1 = 233(7) -102(16)$
Partikulární řešení:
$-59 = 233(59*7) -102(59*16)$
Homogenní řešení:
$0 = 233(x) -102(y)$
### Řešení
1) $ax + by = 0$
- x = 612
- y = 1398
2) 
$(x,y) = (413, 944) + (102t, 233t)$
$t \in Z$
## Příklad
Nechť:
- a = 498
- b = 318
- c = 90