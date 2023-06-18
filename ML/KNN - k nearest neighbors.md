#ML
# KNN
K nejbližších sousedů
Etalony - centroidy
Prahy - nejvzdálenější body (okraj pro odmítnutí)

Není třeba trénovat, ale klasifikace je velmi pomalá. Je nelineární. KNN je robustní i proti šumu v datech.

[[Metriky|Vzdálenostní funkce]]:
- Eukleidovská (přepona)
- Manhattanská (městské bloky)

Pro rozdílné rozsahy je nutná normalizace dat:
- max-min
```
zi = (xi - min(x)) / (max(x) - min(x))
```
	- z € <0,1>
- normalizace (gaussovská, z-skóre)
```
zi = (xi - mean(x)) / G(x)
```
	- zachovává kladné i záporné hodnoty