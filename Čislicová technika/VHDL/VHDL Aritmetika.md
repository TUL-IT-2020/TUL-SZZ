#VHDL 
# Aritmetika
> [!info]
>Něco o aritmetice z oboru číslicové techniky:
>- [[Sčítačky]],
>- [[Odečítání]],
>- [[Násobička]].

## Délky výsledných vektorů

### Sčítání M "+" N
Získáme vektor délky -> $max(M,N)+1$

- $+1$ "cary" - nejvyšší bit operace sčítání
### Násobení M "\*" N
Získáme vektor délky -> $M+N$

## Overflow
Nejvyšší bit na as, bs, xor nesedí s not nejvyšším bytem výsledku operace sčítání.
Přešel jsem přes půlku: 
- z kladných -> záporný
- z záporných <- kladné
## Knihovny pro výpočty ve VHDL

`numeric std`
Přidává nám celočíselné operace.

> [!warning] `math real`
> Nepoužívat pro syntézu. Lze s ní dělat výpočty nad generickými konstantami. 

`whdl real`