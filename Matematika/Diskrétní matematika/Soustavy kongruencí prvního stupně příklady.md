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

40t \equiv 1 (9)
4t \equiv 1 (9)
t = 7
$7*40$

72t \equiv 1 (5)
2t \equiv 1 (5)
t = 3
$3*72$

Výsledná kongruence:
$$
x \equiv \sum_{i=1}^4 c_ib_i (M)
$$
$x\equiv 0*12+ 280*6 + 216*7 + 225*3(360) \equiv 267(360)$

### Řešení
$x \equiv 267(360)$