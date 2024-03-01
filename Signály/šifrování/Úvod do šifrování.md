# Úvod do šifrování
"Gentlemani cizí dopisy nečtou"

- ale kdy chtěli: [www.dcode.fr](https://www.dcode.fr/tools-list)
## Kryptologie
- Kryptografie - šifry
- Kryptoanalýza - lámání šifer

> [!note] "je obtížné ..." 
> Na daný problém zle jít jen hrubou silou (vyzkoušet všechny možné klíče)
>- $10^9$ jader po dobu $10^9$ let na nekvantovém počítači

> [!warning] Terminologie: "šifra" vs. "kód"
>- šifra = kryptografický kód
>- kódové slovo = slovo předem dohodnutého významu

## Vlastnosti šifry
1) Pouze ze znalosti šifrované zprávy je těžké odvodit otevřený text.
2) Ze znalosti šifrované a otevřené zprávy je těžké odvodit klíč. 

> [!important]
>- **Konfůze** - vztah mezi otevřenou a šifrovanou zprávou je co nejsložitější.
>- **Difůze** - informace z otevřeného textu je rozmělněna do celé šifrované zprávy.

## Kerckhoffův princip
![[Kerckhoffův princip]]

## Šifrovací algoritmy
![[rozdeleni_sifer.jpg]]

Šifry:
- symetrické (klasické, jeden klíč pro šifrování a dešifrování)
	- blokové (pracují s celou šifrou)
		- transpoziční (výměna pořadí znaků)
		- substituce (záměna znaků za jiné)
		- kombinace (transpozice + substituce)
	- proudové (pracují byte po bytu)
- asymetrické(s veřejným klíčem)

> [!info] Symetrické
Znalostí šifrovacího klíče je snadné odvodit dešifrovací klíč. 

> [!info] Proudové
Použití: když není jiná možnost (telekomunikace)

> [!tip] Princip: 
>Generátor pseudonáhodných čísel. XOR operace na byte zprávy.
**Klíč**: počáteční stav generátoru 

## Vermanův kryptosystém
![[Vermanův kryptosystém]]

## Blokové symetrické šifry
> [!info] Princip šifrování: 
>- substituce
>- transpozice

proudové vs blokové 

1. Zpráva je rozdělená na bloky.
2. Na ně je aplikována substituce a transpozice

### AES - Advanced Encryption System
![[AES - Advanced Encryption System]]

## Asymetrické systémy
![[Asymetrické systémy]]
## Hybridní kryptosystém
![[Hybridní kryptosystém]]

## Elektronický podpis
![[Elektronický podpis]]
## Kvantová kryptologie
![[Kvantová kryptologie]]