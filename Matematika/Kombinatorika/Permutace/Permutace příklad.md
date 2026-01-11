#příklad 
# Permutace 

## Příklad
$\pi =$ 
1 2 3 4 5 6
2 3 4 5 6 1

### Řešení
Rozklad na disjunktní cykly:
(1 2 3 4 5 6)

Transpozice:
(1 2)(1 3)(1 4)(1 5)(1 6)

## Příklad
$\pi =$
1 2 3 4 5 6 7
3 7 4 1 6 2 5

### Řešení

Rozklad na disjunktní cykly:
(1 3 4)(2 7 5 6)

Transpozice:
(1 3)(1 4) (2 7)(2 5)(2 6)
## Příklad
$\pi =$
1234
3241

$\rho =$
1234
2431
### Řešení
$\pi\rho =$
1234
3412

$\rho\pi =$
1234
2143

$\rho^{-1}\pi^{-1} = (\pi\rho)^{-1} =$
1234
3412

$<\pi>= \left\{\pi^1, \pi^2, \pi^3 \right\}$
$\pi^2=$ 
1234
4213

$\pi^3 =$
1234
1234

$<\pi>$ je třetího řádu
## Příklad
$\pi =$
123456789
952674318

### Řešení
Prohodíme řádky:
$\pi^{-1} =$
952674318
123456789

Součin disjunktních cyklů:
$\pi =$ (198)(2573)(46)

$\pi^{-1} =$ (891)(3752)(64)

$\pi^{2} =$ (198)(2573)(46)(198)(2573)(46) 
= (189)(27)(35)(4)(6)
## Příklad
$\rho, \pi, \sigma, \tau \in S_7$
$\rho =$ (13)(2475)(6)
$\pi=$
1234567
7245631
$\sigma=$
1234567
3425671
$\tau=$ (274563)(1)

### Řešení
Dvojřádkové tabulky:
$\rho =$
1234567
3417265

$\tau=$
1234567
1725634

Součiny disjunktních cyklů:
$\pi=$ (17)(2)(3456)
$\sigma=$ (1324567)

Skládání permutací:
$\pi\rho=$ (17)(2)(3456)(13)(2475)(6) = (156)(24)(37)
$(\sigma^2 \tau)^{-1} = [(1324567)(1324567)(274563)]^{-1} =[(1726)(354)]^{-1} =$ (6271)(453) 
$(\sigma^2 \tau)^{-1} =  \tau^{-1}\sigma^{-2}$

$(\sigma\tau\sigma^{-1})^{-1}=$ (154263)
$(\sigma\tau\sigma)^{-1}=$ (1374)(256)

Vyřešte rovnici: 
$$
(\pi\rho^{-1} x^{-1} \sigma)^{-1}=\sigma^{-1}\rho
$$
$\pi\rho^{-1} x^{-1} \sigma=\rho^{-1}\sigma$
$\pi\rho^{-1} x^{-1}=\rho^{-1}$
$x^{-1}=\rho\pi^{-1}\rho^{-1}$
$x=\rho\pi\rho^{-1}$
$x=$ (13)(2475)(17)(3456)(31)(5742) = (1276)(34)

## Příklad
Uvažujte symetrickou grupu $(S_7,•)$. 
1) Ze vztahu $(\pi • x • \rho^{-1})^{-1}=\rho^{-1}\pi$, kde $\pi, \rho, x \in S_7$ vyjádřete x. Výraz maximálně zjednodušte (výsledný výraz musí obsahovat pouze symboly $\pi, \rho, \pi^{-1},\rho^{-1}$ a jejich součiny). 
2) Spočtěte hodnotu x pro: 
$\pi = (326)(1437)(2641)(537)$,
$\rho = (31)(21)(75)(14)(61)$.
Výsledek zapište ve tvaru součinu disjunktních cyklů!

### Postup
$(\pi • x • \rho^{-1})^{-1}=\rho^{-1}\pi$
$\rho • x^{-1} • \pi^{-1}=\rho^{-1}\pi$
$x^{-1}=\rho^{-2}\pi^{2}$
$x=\pi^{-2}\rho^{2}$

$\pi = (326)(1437)(2641)(537) = (365)(1)(247)$
$\pi^{-1} = (1)(563)(742)$
$\rho = (31)(21)(75)(14)(61) = (32461)(57)$

$x=\pi^{-2}\rho^{2} = (563)(742)(563)(742)(32461)(57)(32461)(57) = (12)(3)(4765)$
### Řešení
$x=(12)(3)(4765)$

## Příklad
Uvažujte permutace $\pi, \rho, \in S_6$, kde:
- $\pi = (13)(42)(65)$,
- $\rho = (215)(3245)(364)(41)(52)$.
1) Vypočtěte $\pi • \rho$, 
2) $\rho^{-1}$, 
3) Výraz $(\pi^{-1} • \rho^{-1})^{-1} • (\rho^{-1}\pi)^{-1}$ nejprve maximálně zjednodušte a následně ho vypočtěte, 
4) Vypište všechny prvky podgrupy grupy $S_6$, která je generovaná permutací $\pi • \rho$. 

Veškeré výsledky uvádějte ve tvaru součinu disjunktních cyklů.
### Postup
Zjednodušení:
$\rho = (16)(24)(35)$

$\pi • \rho = (13)(42)(65)(16)(24)(35) = (15)(2)(4)(36)$

$(\pi • \rho)^2 = (15)(2)(4)(36)(15)(2)(4)(36) = (1)(2)(3)(4)(5)(6) = id$

Úprava výrazu:
$(\pi^{-1} • \rho^{-1})^{-1} • (\rho^{-1}\pi)^{-1}$
$(\rho \pi) • (\pi^{-1}\rho)$
$\rho \pi \pi^{-1} \rho$
$\rho \rho$
$\rho \rho = (16)(24)(35)(16)(24)(35) = (1)(2)(3)(4)(5)(6)$
### Řešení
$\pi • \rho = (15)(2)(4)(36)$
$\rho^{-1} = (61)(42)(53)$
$(\pi • \rho)^2 = id$

## Příklad
V symetrické grupě S, řešte rovnici $axb = ac$, kde:
- a = (123)(54)(67), 
- b = (325)(243)(547), 
- c = (213)(352).

## Příklad

$\pi=$
123456
234561

### Řešení

(123456)

Transpozice:
(12)(13)(14)(15)(16)

## Příklad

$\pi=$
123456
462135
### Řešení
(14)(2653)

Transpozice:
(14)(26)(25)(23)

## Příklad
$\pi=$
12345
14352

Uveďte, které prvky jsou pevné body.

### Řešení
(1)(245)

(24)(25)

1 - pevný bod

## Příklad
$\pi=$
1234567
3741625
### Řešení
(134)(2756)

(13)(14)(27)(25)(26)

## Příklad: Permutace 
Je dána permutace $\pi \in S_8$ ve dvouřádkovém zápisu:
$\pi=$
12345678
31254876

1. Rozložte $\pi$ na součin disjunktních cyklů.
2. Zapište $\pi$ jako součin transpozic (použijte standardní převod cyklu (a1 a2 ... ak) na transpozice (a1 ak)(a1 ak-1)...(a1 a2).

### Řešení
Rozklad na disjunktní cykly:
(132)(45)(68)(7)

Součin transpozic:
(12)(13)(45)(68)