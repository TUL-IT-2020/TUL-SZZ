#příklad
# Kongruence (modulo) 
Vzoreček:
$$
x \equiv (-1)^n*P_{n-1}*b(m)
$$
Kalkulačka online:  [modular-equation-solver](https://www.dcode.fr/modular-equation-solver)
## Příklad
$$185x \equiv 335 mod(435)$$
### Postup
Euklidův algoritmus pro: $a, m$

|  | = |  | x | $q_i$ | + | $r_i$ |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| 435 |  | 185 |  | 2 |  | 65 |
| 185 |  | 65 |  | 2 |  | 55 |
| 65 |  | 55 |  | 1 |  | 10 |
| 55 |  | 10 |  | 5 |  | 5 |
| 10 |  | 5 |  | 2 |  | 0 |
$NSD(a,m)=5$ ... řešení
$37x \equiv 67 mod(87)$ ... a, m jsou nesoudělné -> 1 řešení

Řetězový zlomek pro:
$$\frac{m}{a}$$

| i | -1 | 0 | 1 | 2 | 3 | 4 |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| $q_i$ | / | 2 | 2 | 1 | 5 | 2 |
| $P_i$ | 1 | 2 | 5 | 7 | 40 | 87 |
| $Q_i$ | 0 | 1 | 2 | 3 | 17 | 37 |
Dosazení do vzorečku:
$x \equiv (-1)^4*40*67(87) \equiv 2680(87) \equiv 70(87)$

Pro vytvořeni posloupnosti všech $x$ stačí přičítat zkrácené modulo k našemu prvnímu řešení, dokud je hodnota menší než nezkrácené modulo.
### Řešení
$x \equiv 70, 157, 244, 331, 418 (425)$

## Příklad
$$3 756x \equiv 1 468 mod(680)$$
### Postup
Euklidův algoritmus pro: $a, m$

|  | = |  | x | $q_i$ | + | $r_i$ |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| 680 |  | 3 756 |  | 0 |  | 680 |
| 3 756 |  | 680 |  | 5 |  | 356 |
| 680 |  | 356 |  | 1 |  | 324 |
| 356 |  | 324 |  | 1 |  | 32 |
| 324 |  | 32 |  | 10 |  | 4 |
| 32 |  | 4 |  | 8 |  | 0 |
$NSD(a,m) = 4$ ... řešení
$939x \equiv 367 mod(170)$

Řetězový zlomek pro:
$$\frac{m}{a}$$

| i | -1 | 0 | 1 | 2 | 3 | 4 | 5 |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| $q_i$ | / | 0 | 5 | 1 | 1 | 10 | 8 |
| $P_i$ | 1 | 0 | 1 | 1 | 2 | 21 | 170 |
| $Q_i$ | 0 | 1 | 5 | 6 | 11 | 116 | 939 |
$89x \equiv 27 mod(170)$ ... Po zmodulování do základního tvaru. 

$x \equiv (-1)^5 * 21*27(170)$
$x \equiv -567(170)$
$x \equiv 113(170)$
### Řešení
$x \equiv 113, 283, 453, 623 (680)$

## Příklad
$$
996x \equiv - 396 mod(440)
$$
Soustavu vyřešte. Výsledek zapište v soustavě nejmenších nezáporných zbytků.
Nalezněte nejmenší číslo větší než -1500, které dané kongruenci vyhovuje.

### Postup
Základní tvar:
$116x \equiv 44 mod(440)$

m/a:

|  | = |  | x | $q_i$ | + | $r_i$ |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| 440 |  | 116 |  | 3 |  | 92 |
| 116 |  | 92 |  | 1 |  | 24 |
| 92 |  | 24 |  | 3 |  | 20 |
| 24 |  | 20 |  | 1 |  | 4 |
| 20 |  | 4 |  | 5 |  | 0 |
$NSD(a,m) = 4$
Má 4 řešení.
$29x \equiv 11 mod(110)$

Řetězový zlomek pro:
$$\frac{m}{a}$$

| i | -1 | 0 | 1 | 2 | 3 | 4 |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| $q_i$ | / | 3 | 1 | 3 | 1 | 5 |
| $P_i$ | 1 | 3 | 4 | 15 | 19 | 110 |
| $Q_i$ | 0 | 1 | 1 | 4 | 5 | 29 |

$x \equiv (-1)^4*19*11(110) = 1*209(110)=99(110)$
### Řešení
$x \equiv \{99, 209, 319, 429\} (440)$
$x = -1441$
## Příklad
$$186x \equiv 39 (mod 477)$$
Nalezněte všechna řešení kongruence. Výsledek vyjádřete v soustavě nejmenších nezáporných zbytků modulo m.

### Postup
Podmínka existence řešení: $NSD(a,m) = 1?$

| dělenec | = | dělitel | * | $q_i$ | + | $r_i$ |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| 477 |  | 186 |  | 2 |  | 105 |
| 186 |  | 105 |  | 1 |  | 81 |
| 105 |  | 81 |  | 1 |  | 24 |
| 81 |  | 24 |  | 3 |  | 9 |
| 24 |  | 9 |  | 2 |  | 6 |
| 9 |  | 6 |  | 1 |  | 3 |
| 6 |  | 3 |  | 2 |  | 0 |
$NSD(a,m)=3$ ... řešení
$62x \equiv 13 mod(159)$ ... a, m jsou nesoudělné -> 1 řešení

Řetězový zlomek pro:
$$\frac{m}{a}$$

| i | -1 | 0 | 1 | 2 | 3 | 4 | 5 | 6 |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| $q_i$ | / | 2 | 1 | 1 | 3 | 2 | 1 | 2 |
| $P_i$ | 1 | 2 | 3 | 5 | 18 | 41 | 59 | 159 |
| $Q_i$ | 0 | 1 | 1 | 2 | 7 | 16 | 23 | 62 |
$x = +1*59*13(159) =767(159) = 131$

### Řešení
$x \equiv \{131, 290, 449\} (477)$

## Příklad
$$244x + 340 \equiv 0 (mod 452)$$
Nalezněte řešení kongruence. Řešení zapište v soustavě nejmenších nezáporných zbytků původního modulu.
### Postup
Podmínka existence řešení: $NSD(a,m) = 1?$

| dělenec | = | dělitel | * | $q_i$ | + | $r_i$ |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| 452 |  | 244 |  | 1 |  | 208 |
| 244 |  | 208 |  | 1 |  | 36 |
| 208 |  | 36 |  | 5 |  | 28 |
| 36 |  | 28 |  | 1 |  | 8 |
| 28 |  | 8 |  | 3 |  | 4 |
| 8 |  | 4 |  | 2 |  | 0 |
$NSD(a,m)=4$ ... řešení
$61x \equiv 113-85 mod(113)$ ... a, m jsou nesoudělné -> 1 řešení

Řetězový zlomek pro:
$$\frac{m}{a}$$

| i | -1 | 0 | 1 | 2 | 3 | 4 | 5 |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| $q_i$ | / | 1 | 1 | 5 | 1 | 3 | 2 |
| $P_i$ | 1 | 1 | 2 | 11 | 13 | 50 | 113 |
| $Q_i$ | 0 | 1 | 1 | 6 | 7 | 27 | 61 |
$x = -1*50*28(113)=69$
### Řešení
$x \equiv \{69,182,295,408\} (452)$

## Příklad
$$988x \equiv - 616 mod(708)$$
Soustavu vyřešte. Výsledek zapište v soustavě nejmenších nezáporných zbytků.
Nalezněte nejmenší číslo větší než -2000, které dané kongruenci vyhovuje.

