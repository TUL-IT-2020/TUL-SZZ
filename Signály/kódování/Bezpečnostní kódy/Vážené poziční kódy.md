# Vážené poziční kódy
čísla bankovních účtů, platebních karet, ISBN, rodné číslo

Přidání kontrolní číslice
příklady

| ISBN-10                               |     |     |     |     |     |     |     |     |     |  kontrolní číslice   |
| ------------------------------------- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| ISBN kód |0|5|2|1|8|4|8|6|8|\_|
| Každá pozice má svojí váhu           | 10  | 9   | 8   | 7   | 6   | 5   | 4   | 3   | 2   | 1   |
| Vynásobíme hodnotu číslice její vahou | 0   | 45  | 16  | 7   | 48  | 20  | 32  | 18  | 16  | x   |
| Suma                                  |     |     |     |     |     |     |     |     |     | 202 |

(202 + n) % 11 = 0
n = 7

U bankovních účtů
Váhy: 6|3|7|9|10|8|4|2|1|

Detekují 1 chybu: 
- překlep v číslici
- výměnu číslic
- vynechanou číslici

Detekce 2 chyb na 90%.