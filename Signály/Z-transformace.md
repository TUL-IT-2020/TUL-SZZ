
# Z-transformace
Množina Fourierových transformací. 

$$
X(z) = \sum_{n=-\infty}^{\infty} x[n]z^{-n}
$$

> [!note] ROC - Region konvergnce
>  0blast, kde má řada konečný součet (definiční obor $z$). 

> [!warning]
> Z - transformace existuje, když **jednotková kružnice** leží v regionu konvergence.

## Typy řad:
- levostranná, $(-\infty, -1)$
- pravostranná, $(0, \infty)$

TODO: Tabulku Z-transformace!

## Teorém o posunutí:
$$
x[n-k] \rightarrow z^{-k}X(z)
$$

## Přenosová funkce
Z obraz impulzní odezvy (transfer function).

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

## Příklady
[[Z-transformace příklad]]