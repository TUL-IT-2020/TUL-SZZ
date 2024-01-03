# Lineární kódy se schopností opravy chyb
d = 3 ... minimální vzdálenost pro možnost opravy
$t = \lfloor\frac{d-1}{2}\rfloor$ 

## Počet kontrolních bitů

### 1 kontrolní bit 
Žádní schopnost opravy
### 2 kontrolní bity 
Například: [[Kód(3,1)]]

![[Kód(4,2)]]

2 kontrolní bity => 4 stavy
- bez chyby
- chyba na 1 kontrolním bitu
- chyba na 2 kontrolním bitu
- chyba je ve zprávě
=> Zpráva může mít délku jeden bit.

### 3 kontrolní bity
![[Kód(7,4)]]

Známý také jako [[Hammingův kód]].

## Dodatek k lineárním kódům
### Duální kód
Kód $C(n,k)$, 
matice:
$G_c \; H_c$

Duální kód: $C^\perp(n,n-k)$
platí že matice:
$G_{c^{\perp}} = H_{c}$
$H_{c^\perp}= G_c$

#### Příklad:
Parita (8,7)
H = (1,1,1,1,1,1,1,1)
Duální bude (8,1)
G = (1,1,1,1,1,1,1,1)
- vysíláme bity po 8 a jeden je kontrolní
