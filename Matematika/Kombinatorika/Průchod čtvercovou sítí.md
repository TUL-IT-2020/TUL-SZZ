Čtvercová síť, kde body mají nezáporné celočíselné souřadnice. 

$[x,y]$ - souřadnice bodu

V sítí se pohybujeme pomocí kroků následujících typů:
- $x+1$
- $y+1$

## Cesta z $[0,0] -> [m,n]$
> [!question]
> Určete kolika různými způsoby se lze dostat z bodu $[0,0]$ do bodu $[m,n]$ pomocí uvedených typů kroků.

$[0,0] -> [m, n]$

$m* krok_0$
$n* krok_1$

Bitové řetězce, kde je $m*0$ a $n*1$.
$$
P(m,n) = C_{m+n}^m
$$

## Cesta bez překročení diagonály
> [!question]
> Určete kolika různými způsoby se lze dostat z bodu $[0,0]$ do bodu $[m,n]$ pomocí uvedených typů kroků, bez překročení diagonály.

$m == n$ - prvky diagonály 

Překročit diagonálu:
Vstoupíme do bodu $[x,y]$, kde $y > x$.

$C_n$ - počet cest, tak že nepřekročíme diagonálu.

> [!tip]
$C_n =$ lze spočítat jako počet všech cest a odečteme počet cest kdy překročíme diagonálu.

- $C_n = C_{2n}^n$ - počet všech cest.
- $Z_n$ - počet "zakázaných" cest (překročena diagonála).

### Zakázaná cesta

$$
b_1, b_2, ..., b_k,..., b_{2n}
$$
- $n*0$
- $n*1$
- $b_k$ - pozice kdy poprvé překročíme diagonálu.

$k = 2l+1$ - liché číslo
(diagonála bude $2*l$, tedy sudé číslo)
- $(l+1)*1$
- $l*0$

Připíšeme si před řetězec jednu 0:
$$
0, b_1, b_2, ..., b_k,..., b_{2n}
$$

$0-b_k$ - obsahuje stejný počet nul jako jedniček.

Prohodíme hodnoty na indexu: $i < k+1$
- $b_i = 1, \bar b_i = 0$
- $b_i = 0, \bar b_i = 1$

$$
1, \bar b_1, ..., \bar b_k, b_{k+1},..., b_{2n}
$$
- $(n+1)*0$,
- $n*1$


$Z_n$ - počet zakázaných řetězců = počet bitových řetězců

$$
1, \bar b_1, ..., \bar b_k, b_{k+1},..., b_{2n}
$$
Řetězec obsahující:
- $(n+1)*0$,
- $n*1$,
- začínající $1$.

Hledáme pozici, kdy se počet 0 a 1 vyrovná. To je bod překročení diagonály.

$$
Z_n = P(n+1,n-1) = C_{2n}^{n-1}
$$

$$
C_n = C_{2n}^n - C_{2n}^n-1=
\frac{(2n)!}{n!n!} + \frac{(2n)!}{(n-1)!(n+1)!}
$$

> [!tip] Catalanova čísla
> $\{C_n\}_{n=0}^\infty$ ... Catalanova posloupnost

$$
C_n = \frac{1}{n+1} C_{2n}^n
$$
- $n \in N$
## Další ekvivalentní úlohy?
### Zásobník
$[0,0] -> [n,n]$ - řetězec reprezentující diagonálu

$$
b_1,b_2,...,b_{2n}
$$
- $n*0$
- $n*1$

V libovolném prefixu $b_1,...,b_k$ musí být počet 0 větší nebo roven počtu 1.

WTF: zásobník!
> [!question]
Kolik různých permutací lze získat pomocí zásobníku?


### Závorkování
> [!question]
> Kolika způsoby lze správně uzávorkovat výraz?

- $x_0* x_1* ... * x_n$ - výraz
- $()$ - zvároky
	- $n*($
	- $n*)$

Binární řetězce: $0,1$

Rozdělíme podle posledního uzávorkovaného součinu.
$A,B -> (A*B)$

$x_0 * x_1* x_2* ... * x_n$
$C_0 * C_{n-1}$
$C_1 * C_{n-2}$
...
$C_n * C_0$

$$
C_n = C_0 * C_{n-1} + 
C_1 * C_{n-2} + 
... +
C_n * C_0
$$
- Nelineární
- Homogenní
- Rekurentní vztah řádu: nemá ($n$ - proměnlivého řádu)
	- Jak daleko se musím vrátit abych byl schopen vypočítat daný vztah?
- Počáteční podmínky: $1$
	- $C_0 = 1$

$C_1 = C_0*C_0$

Řešení:
Nemůžeme použít charakteristickou rovnici.

Metoda [[Vytvořující funkce|vytvořujících funkcí]].

## Příklady
- [[Průchod čtvercovou sítí příklady]]
