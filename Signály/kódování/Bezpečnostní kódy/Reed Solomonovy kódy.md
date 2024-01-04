# Reed Solomonovy kódy
Spíše Byte než bity.
Zpráva 3, -1, -2
$y = 3x^2-x-2$
Funkce tvoří parabolu.

Vyhodnotíme v bodech (např: x=0,1,2) a vyjde nám:
$f_y(0) = -2$
$f_y(1) = 0$
$f_y(2) = 8$

-2, 0, 8 -> odešleme

Případně přidáme ke zprávě další body pro redundanci (22,42)

Příjemce hledá polynom 2 stupně, který prochází $[0,-2],[1,0],[2,8]$
S celočíselnými koeficienty. 

## CD disk
1. Data rozdělena na bloky o 24 byte
   - Zakódovány kódem (28,24)
2. Promíchání 28 bloků s krokem 1 zkombinováno tak, že se vezme 1 byte do nového bloku
3. Bloky z kroku 2 se zakódují kódem (32, 28)
