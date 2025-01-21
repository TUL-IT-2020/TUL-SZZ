# Rekurentní vztahy příklady

## Příklad: Trojúhelníková čísla

$$
T_n , 
n \in N^+
$$

$T_3$:

![trojuhelník](https://e7.pngegg.com/pngimages/713/24/png-clipart-triangle-critical-graph-graph-theory-graph-of-a-function-triangle-angle-triangle.png)

$T_n = T_{n-1} + n$
$T_1 = 1$
$T_0 = 0$

Určete rekurentní vztah pro $T_n$.
### Postup

$$
T_n = \frac{n}{2}(n+1)
$$
## Příklad: Rychlý reaktor

- $a$ - rychlé n.
- $b$ - pomalé

$a -> 2a + b$
$b -> a + b$

$a_n, b_n$ - počet částic v čase $n$.

Sestavte soustavu rekurentních vztahů:
### Řešení
$$
a_{n+1} = 2a_n + b_n
$$

$$
b_{n+1} = a_n + b_n
$$

## Příklad: Dva signály 
- $2\mu s$
- $3 \mu s$

$a_n = ?$ - počet všech různých zpráv, které lze z daných signálů sestavit.

### Postup

Zprávu délky $n \cdot \mu s$ lze vytvořit tak, že:
- Přidáme signál délky $2 \mu s$ ke zprávě délky $n - 2  \mu s$,
- Přidáme signál délky $3 \mu s$ ke zprávě délky $n - 3  \mu s$.

To znamená, že počet zpráv $a_n$ je součtem:
$a_n = a_{n-2} + a_{n-3}$

| $a_n$ | počet zpráv | kombinace |
| ----- | ----------- | --------- |
| a_0   | 0           |           |
| a_1   | 0           |           |
| a_2   | 1           | 2         |
| a_3   | 1           | 3         |
| a_4   | 1           | 2+2       |
| a_5   | 2           | 3+2,2+3   |
| ...   |             |           |
### Řešení
Rekurentní vztah 3. řádu.
$a_n = a_{n-2} + a_{n-3}$
- pro n≥4
- $a_0​=0,a_1​=0,a_2​=1,a_3​=1$
charakteristický polynom:
$x^3 -x -1 = 0$
