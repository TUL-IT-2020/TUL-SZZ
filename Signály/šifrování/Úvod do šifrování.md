# Úvod do šifrování
"Gantlemani cizí dopisy nečtou"

## Kryptologie
- Kryptografie - šifry
- Kryptoanalýza - lámání šifer

"je obtížné ..." = na daný problém zle jít jen hrubou silou (vyzkoušet všechny možné klíče)
- $10^9$ jader po dobu $10^9$ let na nekvantovém počítači

Terminologie: "šifra" vs. "kód"

- šifra = kryptografický kód
- kódové slovo = slovo předem dohodnutého významu

## Vlastnosti šifry
1) Pouze ze znalosti šifrované zprávy je těžké odvodit otevřený text.
2) Ze znalosti šifrované a otevřené zprávy je těžké odvodit klíč. 

- **Konfůze** - vztah mezi otevřenou a šifrovanou zprávou je co nejsložitější.
- **Difůze** - informace z otevřeného textu je rozmělněna do celé šifrované zprávy.

## Kerckhoffův princip
(Období první světové války)
Bezpečnost šifry je v klíči ne v metodě.

Klíč je "spotřební materiál".
Bezpečnost je dána délkou a náhodností klíče (entropie).
šifrování $O(n), O(n^e)$ s délkou klíče $1<e<2$
útok hrubou silou $O(2^n)$

## Šifrovací algoritmy
![[rozdělení šifer.jpg]]

Šifry:
- symetrické (klasické, jeden klíč pro šifrování a dešifrování)
	- blokové (pracují s celou šifrou)
		- transpoziční (výměna pořadí znaků)
		- substituce (záměna znaků za jiné)
		- kombinace (transpozice + substituce)
	- proudové (pracují byte po bytu)
- asymetrické(s veřejným klíčem)

Symetrické
Znalostí šifrovacího klíče je snadné odvodit dešifrovací klíč. 

Proudové
Použití: když není jiná možnost (telekomunikace)
Princip: 
Generátor pseudonáhodných čísel. XOR operace na byte zprávy.
Klíč: počáteční stav generátoru 

## Vermanův kryptosystém
(šifra jednorázovou tabulkou)
100% bezpečnost (teoreticky)
- Klíč je zcela náhodný.
- Klíč je stejně dlouhý jako zpráva.
- Klíč se použije jen jednou

Problém:
- získat opravdu náhodný klíč
- spotřeba klíče
- zaručení jedno použití
- skladování klíče

## Blokové symetrické šifry
Princip šifrování: 
- substituce
- transpozice

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