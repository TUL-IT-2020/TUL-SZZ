# Úlohy s věžovými polynomy
> [!question] Cíl:
Určit koeficienty $r(x_i, C)$

## Počáteční podmínky
$r_0(C) = 1$ ... žádná věž na šachovnici
$r_1(C) =$ počet přípustných polí šachovnice $C$ 

## Případy

### Dvě disjunktní pod-šachnovnice
Nechť $C$ je šachovnice, která se skládá z pod-šachovnic $c_1$ a $c_2$, které jsou řádkově a sloupcově disjunktní. 
Tedy žádné přípustné pole $c_1$ neleží ve stejném řádku ani sloupci s přípustným polem $c_2$. Potom: 
$$
r_k(c) = \sum_{i=0}^k r_i(c_1) * r_{k-i}(c_2)
$$
Respektive:
$$
r_k(c) = r(x,c_1) * r(x,c_2)
$$
> [!note] konvoluce
> Součin vytvořujících funkcí.

#### Jdeme dokazovat:

| $c_1$ | $c_2$ | $r_k(c)$                |
| ----- | ----- | ----------------------- |
| 0     | k     | $r_0(C_1)*r_k(C_2)$     |
| 1     | k-1   | $r_1(C_1)*r_{k-1}(C_2)$ |
| ...   |       | ...                     |
| k     | 0     | $r_k(C_1)*r_0(C_2)$     |

$$
r_k(c) = \sum_{i=0}^k r_i(c_1) * r_{k-i}(c_2)
$$
Vynásobíme $x^k$

$$
r_k(c)*x^k = \sum_{i=0}^k r_i(c_1)x^i * r_{k-i}(c_2)x^{k-i}
$$

$$
r(x,C) = r(x, c_1) * r(x,c_2)
$$

### Více disjunktních šachovnic
> [!tip]
Šachovnice $C$ se skládá z pod-šachovnic $C_1, ... , C_l$, které jsou po dvou řádkově sloupcově disjunktní. 
Tedy: $\forall i \neq j C_i a C_j$ jsou řádkově i sloupcově disjunktní.

Potom:
$$
r(x,c) = \prod_{i=1}^l r(x,c_i)
$$

> [!note] Pravidlo vyloučení třetího (Pravidlo faktorizace)
Buď platí a nebo neplatí a, není třetí možnost.

Na šachovnici $C$ je vždy alespoň jedno přípustné pole.
Pak věž umístíme věž na libovolné pole.
A umístíme k věží na pod-šachovnici s disjunktními sloupci a řádky.

Nechť $C$ je šachovnice a $p$ je libovolné její přípustné pole. Potom:
$$
r_k(C) = r{k-1} (C_1) + r_k (C_2)
$$
Respektive:
$$
r(x,C) = xr(x,C_1) + r(x, C_2)
$$
> [!example] kde:
- $C_1$ je pod-šachovnice, která vznikne z $C$ vynecháním řádku a sloupce na jejichž průsečíku je zvolené pole $p$.
- $C_2$ je pod-šachovnice, která vznikne z $C$ vynecháním pole $p$ (tj. pole $p$ zakážeme).

Tedy: buď věž dáme na políčko (a umísťujeme o jednu věž méně), nebo to políčko zakážeme (a umísťujeme stále stejný počet věží).
