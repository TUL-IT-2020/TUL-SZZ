
#příklad
# Příklad paralelní systém

## Příklad
Jak se zrychlí výpočet dvou procesorového systému, jestliže 80 % výpočetního algoritmu lze paralelizovat? (přidali jsme druhý procesor)

### Postup
#### Vzorec
- $f_p = 0.8$
- $p = 2$
$$
S = \frac{1}{
(1-0.8)+\frac{0.8}{2}
} = 1,67
$$
#### Tabulka
| \ | $T_{old}$ | Zrychlení | $T_{new}$ |
| ---- | ---- | ---- | ---- |
| seqvenčně | 0.2 | 1/1 | 0.2 |
| paralelizovatelné | 0.8 | 1/2 | 0.4 |
| sum() | 1 |  | 0.6 |
$$
S = \frac{1}{0.6} = 1,67
$$
### Řešení
Dojde k zrychlení o $67\%$.