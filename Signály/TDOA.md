### TDOA
Hledání směru příchozího signálu za pomoci dvou mikrofonů.

Signál dorazí na mikrofony v různém čase. 
- $d$ - vzdálenost mikrofonů
- TDOA - time diference of arrival

Musíme přepočítat počet vzorků:
$l_{MAX}*T_s$
> [!tip] Úhel mluvčího
$$
DOA = arcsin(\frac{TDOA*c}{d})
$$
- $DOA$ - direction of arrival $[DEG]$
- $c$ - speed of sound