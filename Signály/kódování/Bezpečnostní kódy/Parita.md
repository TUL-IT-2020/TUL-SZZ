# Parita
Ke každé n-tici bitů zprávy přidá bit tak, aby výsledný počet 1 (nebo 0) ve slově o n+1 bitech byl sudý (lichý).

Odesilatel:
110110(0) 111001(0) 000100(1)

Příjemce:

| Data      | vyhodnocení parity | validnost zprávy |
| --------- | ------------------ | ---------------- |
| 110110(0) | OK                 | OK               |
| 101001(0) | NOK                | NOK              |
|   100100(0)        |         OK           |      NOK            |

Detekuje lichý počet chyb ve slově. Pouze detekuje, neopravuje. 