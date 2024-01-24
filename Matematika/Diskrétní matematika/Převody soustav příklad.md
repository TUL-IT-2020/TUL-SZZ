#příklad 
# Převody soustav
Pro kontrolu:
- [převody soustav](https://veiner.eu/matematika/prevody.php)
- [Number Converter](https://www.rapidtables.com/convert/number/)
## Příklad

$$
(1234)_{10} = ?_8
$$

### Postup
$1234 = 8q_1 + r_0$

| Podíl |  | Zbytek |  |
| ---- | ---- | ---- | ---- |
| $q_1$ | 154 | $r_0$ | 2 |
| $q_2$ | 19 | $r_1$ | 2 |
| $q_3$ | 2 | $r_2$ | 3 |

### Řešení
$$
(1234)_{10} = 2322_8
$$

## Příklad
$$
(-1234)_{10} = ?_2
$$

$(-1234)_{10} = 2^{16}-1234_{10}$

## Příklad

$$
3254_7 = ?_{13}
$$
### Postup
Převod do soustavy o základu 10 ("hodnota v polynomu v bodě").

| cifra | x   | řád | =   | násobek |
| ----- | --- | --- | --- | ------- |
| 4     |     | 7^0=1    |     | 4        |
| 5     |     | 7^2    |     | 35        |
| 2     |     | 7^3    |     | 98        |
| 3     |     | 7^4    |     | 1029        |
|       |     |     |     | sum()        |
|       |     |     |     | 1166        |
Dělíme základem nové soustavy:

| dělenec | : | dělitel | = |  | + | zbytek |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| 1166 |  | 13 |  | 89 |  | 9 |
| 89 |  | 13 |  | 6 |  | 11 |
| 6 |  | 13 |  | 0 |  | 6 |

Nejnižší zbytek odpovídá nejvyššímu řádu v nové soustavě. 
### Řešení
$$
3254_7 = 6b9_{13}
$$

## Příklad

$$
ac3d_{14} = ?_{8}
$$
### Postup
$$
ac3d_{14} = 29847_{10}
$$

| dělenec | : | dělitel | = |  | + | zbytek |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| 29847 |  | 8 |  | 3730 |  | 7 |
| 3730 |  | 8 |  | 466 |  | 2 |
| 466 |  | 8 |  | 58 |  | 2 |
| 58 |  | 8 |  | 7 |  | 2 |
| 7 |  | 8 |  | 0 |  | 7 |
### Řešení

$$
ac3d_{14} = 72227_{8}
$$

## Příklad
Převod je jednoduchý ze soustav jejichž základ je mocninou původního.
(2 -> 16)

$$
2012021_3 = ?_9
$$
### Postup
Rozdělíme číslo po dvou cifrách ($3^2 = 9$).
$21_3 \rightarrow 2*3+1 = 7_D$
$20_3 \rightarrow 2*3 + 0 = 6_D$
$1_3 \rightarrow 1_D$
$2_3 \rightarrow 2_D$
Seskládáme nové číslo.
### Řešení
$$
2012021_3 = 2167_9
$$
## Příklad
$$
8fe5_{27} = ?_3
$$
### Postup
| cifra | hodnota | $\rightarrow$ | 9 | 3 | 1 |
| ---- | ---- | ---- | ---- | ---- | ---- |
| 5 | 5 |  | 0 | 1 | 2 |
| 8 | 8 |  | 0 | 2 | 2 |
| e | 14 |  | 1 | 1 | 2 |
| f | 15 |  | 1 | 2 | 0 |
### Řešení
$$
8fe5_{27} = 22120112012_3
$$
