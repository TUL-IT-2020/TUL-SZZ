# Instantní kódy
Instantní kódy (okamžité), lze je dekódovat jak postupně kódy přichází.

``` mermaid
stateDiagram-v2
    state Kódy {
    state Regularní_kódy {
    state Jednoznačné_kódy {
    state Instantní_kódy {
    state Blokové_kódy {
    *
    }
    }
    }
    }
    }
```

## Binární strom
``` mermaid
flowchart TB
    A((E))
    B(((0)))
    C((1))
    A --- |0 Je kódové slovo| B
    A --- C
    
    D((00))
    E((01))
    B --x D
    B --x E
	
    F((10))
    G((11))
    C --- F
    C --- G
```

Příklad IK pro tři slova:
``` mermaid
flowchart TB
	A((*))
    A --- C((*))
    A --- B((*))
    
	B --- E((*))
	B --- D((*))
	
```
Kód slova: $0,10,11$


čtyři slova
``` mermaid
flowchart TB
	A((*))
    A --- C((0))
    A --- B((*))
    
	B --- E((10))
	B --- D((*))
	
	D --- F((110))
	D --- G((111))
```
Kód slova: $0, 10, 110, 111$
``` mermaid
flowchart TB
	A((*))
    A --- B((*))
    A --- C((*))
    
	B --- E((00))
	B --- D((01))
	
	C --- F((10))
	C --- G((11))
```
Kód slova: $00, 01, 10, 11$


pět slov
``` mermaid
flowchart TB
	A((*))
    A --- B((*))
    A --- C((*))
    
	B --- D((*))
	B --- E((*))
	
	C --- F((*))
	C --- G((*))

	G --- H((*))
	G --- I((*))
```
Délka kódu: $3*2+2*3=12$

``` mermaid
flowchart TB
	A((*))
    A --- B((*))
    A --- C((*))
    
	C --- D((*))
	C --- E((*))
	
	E --- F((*))
	E --- G((*))

	G --- H((*))
	G --- I((*))
```
Délka kódu: $1+2+3+4+4 = 14$

``` mermaid
flowchart TB
	A((*))
    A --- B((*))
    A --- C((*))
    
	C --- D((*))
	C --- E((*))
	
	D --- F((*))
	D --- G((*))

	E --- H((*))
	E --- I((*))
```
Délka kódu: $1+4*3 = 13$

### Délka kódu
$L_k = \frac{1}{N} \sum^n_{i=1} l_i$
- $n$ - počet kódových slov
- $l_i$ - délka í-tého kódového slova
Měřítko jestli kód je dobrý nebo špatný pouze tehdy, když mají všechny kódová slova stejnou pravděpodobnost výskytu. 

### Průměrná délka kódu
$L_{AV} = \frac{1}{n} \sum^n_{i=1} l_i p_i$
- $p_i$ - pravděpodobnost výskytu i-tého znaku
Efektivní kód: znaky s vysokou pravděpodobností jsou krátká kódová slova.

### Kraftova nerovnost (pro binární kódy)
$\sum^n_{i=1} 2^{-l_i} \leq 1$
TODO: Co nám říká?

Jednoznakové kódové slovo sebere polovinu stromu, vyplatí se nám použít u znaků s vyšší jak 50% výskytem.

## Optimální instantní kód
- $n$ - znaků
- $p_1, p_2, ..., p_n$
	- $p_i$ ... pravděpodobnost výskytu

Nutná podmínka:
$p_1 \geq p_2 \geq p_3 \; ... \geq p_n$
$l_1 \leq l_2 \leq l_3 \;\; ... \leq l_n$

- $l_i$ - délka 

### Huffmanova konstrukce
![[Huffmanovo kódování]]