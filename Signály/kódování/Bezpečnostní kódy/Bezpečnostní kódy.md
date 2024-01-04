# Bezpečnostní kódy

Chyby přenosu po komunikačním kanále. 

Detekce (oprava) chyby při přenosu informace. 

``` mermaid
flowchart LR
	Z["Zdroj informace"] 
	V["Vysílání"] 
	p["přijímac"]
	P["Přijemce"] 
	Š["Zdroj šumu"]
	
	
	Z ---> V
	V -- komunikační kanál --> p
	p ---> P
	Š ---> p	
```

Nezávislé chyby - bílý šum

``` mermaid
flowchart LR
	subgraph Vstup
		I
		O
	end
	subgraph Výstup
		i
		o
	end
	O -- "(1-p)" --> o
	O -- p --> i
	I -- "(1-p)" --> i
	I -- p --> o
``` 
$p = \frac{1}{2}$

Reálně p cca $10^{-5}$ a méně.

Pdp chyby na 1 bitu P
Délka zprávy ... n bitů
Pdp zprávy bez chyby = $(1-p)^n$

$(1 - \frac{1}{n})^n -> \frac{1}{e}$

## Volební kódy
Každý bit vysíláme nx-krát.
Příklad: ![[Kód(3,1)]]

## Parita
![[Parita]]

## "Sloupcová parita"
![[Sloupcová parita]]

## CRC - Cyclic Redundancy Check
![[CRC]]
## Vážené poziční kódy
![[Vážené poziční kódy]]

## Lineární kódy
![[Lineární kódy]]

### Lineární kódy se schopností opravy chyb
![[Lineární kódy se schopností opravy chyb]]