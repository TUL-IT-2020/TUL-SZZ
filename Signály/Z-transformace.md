# Z-transformace
Množina Fourierových transformací. 
## Obecný předpis
$$
X(z) = \sum_{n=-\infty}^{\infty} x[n]z^{-n}
$$

$$
X[z]=x[0]+x[1]z^{-1}+...x[N]z^{-N}
$$
Operátor $z^{-1}$ znamená zpoždění o 1 vzorek.

> [!note] ROC - Region konvergnce
>  Oblast, kde má řada konečný součet (definiční obor $z$). 

> [!warning]
> Z - transformace existuje, když **jednotková kružnice** leží v regionu konvergence.

Převádí časový popis číslicových signálů do komplexní roviny, kde lze snáze studovat chování systémů a jejich frekvenční charakteristiky.

## Typy řad:
- levostranná, $(-\infty, -1)$
- pravostranná, $(0, \infty)$

TODO: Tabulku Z-transformace!

## Teorém o posunutí:
$$
x[n-k] \rightarrow z^{-k}X(z)
$$

## Přenosová funkce
Z obrazu impulzní odezvy (transfer function).

Frekvenční charakteristika $H(z)$:
$$
H(e^{j\omega}) 
$$
- $z = e^{j\omega}$

## Nuly a póly
Kořenové činitelé:
- Nuly - kořeny čitatele
- Póly - kořeny jmenovatele

> [!warning]
> Pól nesmí ležet na jednotkové kružnici.

> [!tip]
> Region konvergence nemůže obsahovat póly (z definice).

Matlab: 
- `zplane`, graf s póly a nulami
- `[z, p, k] = residuez([])`, parciální zlomky
	- `z` - čitatele,
	- `p` - póly,
	- `k` - čely po částečném dělení.

## Inverzní systém
$$
G(z) = \frac{1}{H(z)}
$$
[[Z-transformace příklad inverzních filtrů]]
## Příklady
[[Z-transformace příklad]]