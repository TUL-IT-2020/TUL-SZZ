# Spolehlivost

- Zjišťování ... měření
- Předvídání ... predikce
- Řízení ... FMECA

> [!tip] Spolehlivost
> Schopnost plnit požadovanou funkci v daném čase a podmínkách.

dependebility:
- bezporuchovost, udržovatelnost, ...

## Terminologie
Dependability - provozní spolehlivost
reliability - spolehlivost
availability - pohotovost (funkční poměr času)
safety - bezpečnost (při selhání nepůsobí další škody)
performability - proveditelnost (dojezd do servisu v Nouzovém režimu)
maintanability - udržovatelnost (opravitelnost)
testability - testovatelnost 
## Pravděpodobnost poruchy
Distribuční funkce. V nekonečnu se vše rozbije.
> [!tip] Q(t) - unreliability
> - pravděpodobnost, že porucha nastane do doby t
- Q(t) = 1 - F(t)
- 0 <= Q(t) <= 1
- Q v nekonečnu je 1

### Empirická hodnota:
$$
\hat Q(t) = \frac{n(t)}{\bar n}
$$
- $n (t)$ - počet poruch, do doby t
- $\bar n$ - počet zařízení

## Hustota poruch:
$$
f(t) = \frac{dQ(t)}{dt}
$$

### Empiricky:
$$
\hat f(t) = \frac{\bar n (t+ \Delta t) - \bar n (t)}{n \cdot \Delta t}
$$

## Pravděpodobnost bezporuchového stavu
> [!tip] R - reliability
> - pravděpodobnost, že porucha nenastane do doby t
$$
R(t) = 1 - Q(t)
$$
- t - doba do poruchy
- 0 <= R(t) <= 1
- R v nekonečnu je 0

## Intenzita poruch
$$
\lambda(t) = \frac{f(t)}{R(t)} = \frac{f(t)}{1 - Q(t)}
$$
jednotka:
- $h^{-1}$ - hodina na -1


Počet porušených za dt.
Ku
Počtu neporušených krát dt.
## Střední doba do poruchy:
$$
T = 1/ \lambda
$$
- polovina výrobků se porouchá do doby T.

MTTF - mean time to failure
Střední doba do "první" poruchy.

### Vanová křivka
"Bath curve"
- Velké množství poruch na začátku, pak klesá.
- Pak užitečná životnost.
- Pak opět vzrůstá, končí se životnost.

## Modely systému
### Sériový model
Každý prvek musí pracovat správně, aby pracoval správně celý systém – žádná redundance.
![[2.gif]]

Spolehlivost:
$$
R_s(t) = \prod_{i=1}^n R_i(t)
$$
s - sériově
Produkt všech dílčích spolehlivostí. $R \leq 1$ čím více prvků, tím menší spolehlivost.  
### Paralelní model
Stačí, aby správně pracoval jeden prvek.
![[levy.gif]]

Poruchovost:
$$
Q_p(t) = \prod_{i=1}^n Q_i(t)
$$
p - paralelně

Spolehlivost:
$$
R_p(t) = 1 - \prod_{i=1}^n (1 - R_i(t))
$$
Porucha systému nastane až při poruše všech prvků současně.