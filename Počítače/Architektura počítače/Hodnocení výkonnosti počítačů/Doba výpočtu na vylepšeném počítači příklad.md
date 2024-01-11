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