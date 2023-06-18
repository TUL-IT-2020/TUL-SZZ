#ML
# SVM
Support Vector Machine
Přímka s maximální možnou vzdáleností od nejbližších reprezentantů obou tříd.
„max-margin“ klasifikátor
```Python
# 1 ... margin
# 𝑦𝑖 ∈ {−1, +1}
𝑦𝑖*(𝒙𝑖𝑇 * 𝒘 + 𝑏) ≥1
```

## Soft margin SVM
SVM s měkkým okrajem. Pro některé body nemusí platit podmínka: 
```Python
# Podmínka:
yi*(𝐱iT * 𝐰 + b) ≥ 1

# Přejde na:
yi*(𝐱iT * 𝐰 + b) ≥ 1 − 𝜉𝑖
𝜉𝑖 ≥ 0

# Minimalizujeme:

# Za podmínky:
# K - sířka tolerančního pásma
1/2*||w,b||^2 + K*SUM(𝜉𝑖)
𝜉𝑖 = 𝑚𝑎𝑥(0,1 − 𝑦𝑖(𝒙𝑖𝑇*𝒘 + 𝑏))
```

V rámci minimalizace minimalizujeme i součet rozvolňujících proměnných. 
Pro body, které leží mimo okraj je vypočtená hodnota větší než jedna. max(0, 1 - vzdálenost) je pak záporné číslo a maximum se tedy bere nula, díky čemuž se při učení již neaplikuje.

![[Porovnání SVM a logistické regrese.png]]