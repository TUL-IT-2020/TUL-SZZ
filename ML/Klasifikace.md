# Klasifikace

## KNN
![[KNN - k nearest neighbors]]

## MLE
![[MLE - Maximum Likelihood Estimation]]

## SVM
![[SVM - Support Vector Machine]]

## Lineární klasifikace do více tříd:
- 1 vs 1 a majoritní hlasování
- 1 vs REST a majoritní hlasování
- 1 vs REST a výběr dle maximálního skóre
	- Hledá se nejbližší vzdálenost k oddělovací přímce.
- SOFTMAX (zobecnění sigmooidy)

**Softmax**
Součet všech výstupů je roven 1.
Pravděpodobností. 
Není potřeba počítat při klasifikaci, pouze při trénování.
```
SMAX(u) = (e^ui)/sum(e^u)
```
### SGD
```
Yp = SMAX(XT * 𝜃)
𝜃t+1 = 𝜃t - 𝛼*X*(Yp - Y)
Y one hot encoding
```

![[Porovnání řešení s SGD 2.png]]
