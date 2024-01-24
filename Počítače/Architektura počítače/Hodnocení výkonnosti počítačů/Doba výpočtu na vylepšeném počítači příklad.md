#příklad 
# Doba výpočtu na vylepšeném počítači příklad
## Příklad
Předpokládejme, že výpočet trvá 30 % času, zbytek času je nevyužit či se čeká na I/O. Dále předpokládejme, že výpočet můžeme 5× zrychlit. Jaká bude celková hodnota zrychlení?

### Postup
- $F_E = 0.3$
- $S_E = 5$
$$
S_{cel} = \frac{1}{
(1-0.3) + \frac{0.3}{5}
} = \frac{1}{0.76}
= 1.316
$$
### Řešení
Z výpočtu je vidět, že systém bude zrychlen přibližně o 31,6 %.

## Příklad

| \    | $T_{old}$ | Zrychlení | $T_{new}$ |
| --- | --------- | --------- | --------- |
| $P_1$    | 0.11      | 1/1       | 0.11      |
| $P_2$    | 0.18      | 1/5       | 0.036     |
| $P_3$    | 0.23      | 1/20      | 0.0115    |
| $P_4$    | 0.48      | 1/1.6     | 0.3       |
| sum()    | 1         |           | 0.4575    |
$$
S = \frac{T_{old}}{T_{new}} = \frac{1}{0.4575} = 2.19
$$
### Řešení
Zrychlení systému bude o $119\%$ .
