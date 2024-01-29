#příklad 
# Grupy

## Příklad
Uvažujte množinu čísel $\{a + b \sqrt{2} \; | \; a, b \in Z\}$. 
Rozhodněte, zda daná množina tvoří: 
1) grupu vzhledem k násobení, 
2) grupu vzhledem ke sčítání, 
3) těleso. 

Svá tvrzení řádně zdůvodněte.
### Postup
Grupa splňuje:
![[Grupy#Grupy]]

Pro násobení:
$$
\left((a_1 + b_1 \sqrt{2}) * (a_2 + b_2 \sqrt{2}) \right) * (a_3 + b_3 \sqrt{2}) =? \; (a_1 + b_1 \sqrt{2}) * \left((a_2 + b_2 \sqrt{2}) * (a_3 + b_3 \sqrt{2}) \right)
$$

$e = 1 + 0\sqrt{2}$

$1 = (a_1 + b_1 \sqrt{2}) * 1/(a_1 + b_1 \sqrt{2})$
Inverzní prvek nelze vyjádřit.

Netvoří grupu pro násobení.

Pro sčítání:
$(a_1 + b_1 \sqrt{2} + a_2 + b_2 \sqrt{2} ) + a_3 + b_3 \sqrt{2} = a_1 + b_1 \sqrt{2} + (a_2 + b_2 \sqrt{2} + a_3 + b_3 \sqrt{2} )$

$a + b \sqrt{2} + 0 + 0\sqrt{2} = a + b \sqrt{2}$
$e = 0 + 0\sqrt{2}$

$0 + 0\sqrt{2} = a_1 + b_1 \sqrt{2} + (-a_1 -b_1 \sqrt{2})$
$\bar a = -1( a_1 + b_1 \sqrt{2})$

Pro sčítání množina tvoří grupu.

Těleso je množina se dvěma operacemi. Pokud je tedy grupa s čítáním i násobením, pak tvoří těleso.

## Příklad
Uvažujte grupu $(Z^{*}_{18},•)$. 
1) Sestavte tabulku, jejíž první řádek bude obsahovat všechny prvky dané grupy (řazené vzestupně) a druhý řádek jim odpovídající inverzní prvky. 
2) Určete všechny generátory dané grupy.

### Postup
$Z^*_{18}$ ... redukovaná soustava zbytků modulo 18.

Rozklad modulu na prvočísla:
$18 = 2*3^2$

Zbytky nesoudělné s modulem:
$\varphi(18) = (2-1)(3^2-3) = 6$ ... bude jich
$Z^*_{18} = \{1, 5, 7, 11, 13, 17\}$

Generátory dané grupy:
$<x> =? Z^*_{18}$

| $x^1(18)$ | 1 | 5 | 7 | 11 | 13  | 17 |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| $x^2(18)$ | 1 | 7 | 13 | 13 | 7 | 1 |
| $x^3(18)$ |  | 17 | 1 | 11 | 1 |  |
| $x^4(18)$ |  | 13 |  | 7 |  |  |
| $x^5(18)$ |  | 11 |  | 5 |  |  |
| $x^6(18)$ |  | 1 |  | 1 |  |  |
$Z^*_{18} = <5> = <11>$
$<7> = <13>$

Inverzní prvky:

| x | 1 | 5 | 7 | 11 | 13 | 17 |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| inverzní | 1 | 11 | 13 | 5 | 7 | 17 |
