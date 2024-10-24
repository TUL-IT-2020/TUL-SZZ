# Rekurentní vztahy příklady

## Fibonacciho úloha

| n   | F_n | poznámka                                 |
| --- | --- | ---------------------------------------- |
| 0   | 0   | prázdný ostrov                           |
| 1   | 1   | po měsící vysasdíme jeden pár králíků    |
| 2   | 1   | Za další měsíc králíci dospějou.         |
| 3   | 2   | Druhý měsíc de jim narodí další králíci. |
|     |     |                                          |
| 12  | ?   | Počet králíků po roce.                   |
$F_{12} = ?$

### Postup:
$F_n = \forall$

Hom. lin. rk. :
$F_n = F_{n-1} + F_{n-2}$
$F_n+2 = F_n+2 - F_n = 0$

Počáteční podmínky:
- $F_0 = 0$
- $F_1 = 1$

## Hanojské věže

Klášter v Hanoi, mají tam desku a tři tyče. 64 seřazených disků od nejmenšího po největší.

1) Vždy lze přemístit jen jeden disk, který lze umísti na libovolnou tyč.
2) Vždy lze umístit pouze menší disk na větší.

> [!warning] 
> Až to mniši přerovnají přijde konec světa!

$A_n$ ... Optimální Počet kroků k přemístění $n$ disků  

a_n = 2a_n-1 +1  
a_0 = 0  
a_1 = 3  
7  
  
2^n-1  
  
Jedno 64b slovo  

## Počet zrnek na šachovnici