#příklad
# Příklady

## Příklad 1.

Je dána zdrojová abeceda A,B,C,D. 
Pravděpodobnosti výskytu jednotlivých znaků jsou: p(A) = 0.4, p(B) = 0.3, p(C) = 0.2 a p(D) = 0.1.  
Zakódujte zprávu ADCB aritmetickým kódováním.  

Jaká je minimální a maximální délka zprávy než bude dosaženo strojové přesnosti typu float (IEE754, 32-bit)?

### Postup
| Abeceda        | počátek | A   | B   | C   | D   |
| -------------- | ------- | --- | --- | --- | --- |
| Pravděpodbnost | 0       | 0.4    | 0.3    | 0.2    | 0.1    |
| Počátek kumulativni    | x        | 0    | 0.4    | 0.7    | 0.9    |
- $\alpha_j$ - počátek intervalu
- $l_j$ - šířka intervalu

Výpočet dalšího $\alpha$:
$\alpha_{n+1} = \alpha_n + l_n * \sum{p_k}$

- $P$ - pravděpodobnosti srovnané od nejvyšší
- $\sum_{i=0}^{k}{P_i}$ - kumulativní pravděpodobnost
	- $k$ - index pro kódovaný znak

Výpočet dalšího $l$:
$l_{n+1} = l_n * P_k$

- $P_k$ - pravděpodobnost daného znaku

| znak | $\alpha_j$ | $l_j$ | výpočet | výpočet |
| ---- | ---- | ---- | ---- | ---- |
| / | 0 | 1 |  |  |
| A | 0 | 0.4 | 0+0 | 1*0.4 |
| D | 0.36 | 0.04 | 0 + 0.4*0.9 | 0.4*0.1 |
| C | 0.388 | 0.008 | 0.36 +0.04*0.7  | 0.04*0.2 |
| B | 0.3912 |  | 0.388 + 0.008*0.4 | 0.008*0.3 |
### Řešení
Interval (0.3912, 0.3936)  
Minimální délka 7 znaků (samá 'D') - dosáhneme délky intervalů okolo 10^-7, což je strojová přesnost 32-bitového float-u.  
Maximální délka 17 znaků (samá 'A') - 0.4^17 = 1.72*10^-7

## Příklad 2.

Je dána zdrojová abeceda A,B,C,D,E. 
Pravděpodobnosti výskytu jednotlivých znaků jsou: p(A) =  p(B) = p(C) = p(D) = p(E) = 0.2. 

Aritmetickým kódováním byla zakódována zpráva o délce čtyři znaky. Zpráva po zakódování je číslo 0.385.  
Jaká je nezakódovaná zpráva?

### Postup

| Abeceda | počátek | A | B | C | D | E |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| Pravděpodbnost | 0 | 0.2 | 0.2 | 0.2 | 0.2 | 0.2 |
| Počátek kumulativni | x | 0 | 0.2 | 0.4 | 0.6 | 0.8 |
$R = 0.385$

| $\alpha_j$ | $l_j$ | $\frac{R-\alpha_j}{l_j}$ | znak | výpočet |
| ---- | ---- | ---- | ---- | ---- |
| 0 | 1 | 0.385 | B | 0.385 < 0.4 |
| 0.2 | 0.2 | 0.925 | E | 0.925 < 1 |
| 0.36 | 0.04 | 0.625 | D | 0.625 < 0.8  |
| 0.384 | 0.008 | 0.125 | A | 0.125 < 0.2 |
Dekódovali jsme 4 znaky, algoritmus končí.
### Řešení

BEDA

