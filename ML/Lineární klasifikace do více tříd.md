#ML
# Lineární klasifikace do více tříd
- 1 vs 1 a majoritní hlasování
- 1 vs REST a majoritní hlasování
- 1 vs REST a výběr dle maximálního skóre
	- Hledá se nejbližší vzdálenost k oddělovací přímce.
- [[Softmax|SOFTMAX]] (zobecnění [[Sigmoid|sigmooidy]])

## One-hot encoding

## SGD
```
Yp = SMAX(XT * 𝜃)
𝜃t+1 = 𝜃t - 𝛼*X*(Yp - Y)
Y one hot encoding
```

![[Porovnání řešení s SGD 2.png]]