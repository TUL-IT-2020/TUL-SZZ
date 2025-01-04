# Float, double
Reprezentace desetinných čísel užitím celočíselných formátů
Nepřesné, Nízký dynamický rozsah

![[float.png]]

Řešení:
Užití komplexního (složeného) datového typu (float)
S = znaménko 1 = -1, 0 = 1;
Biasovaný exponent = E + Bias(127)
Mantisa = 1, Fraction

Součástí C99 jako IEEE754
32bit float a 64bit double, 80-128bit long double

## Počítáme ve floatu
### Násobení
znásobení mantis, sečtení exponentů, zaokrouhlení nebo oříznutí
Násobení
Denormalizace na stejný exponent

### Sečtení
Normalizace s úpravou exponentů