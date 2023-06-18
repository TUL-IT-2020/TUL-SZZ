#ML
# Binární lineární klasifikace
Model perceptronu.

## Regrese a Logistická regrese
Modely jsou podobné, ale liší se použitím aktivační funkcí [[Sigmoid|sigmoid]] u logistické regrese, který vyjadřuje pravděpodobnost.

### Učení
Parametrem, který se učí, je vektor vah **w**. Hodnoty tohoto vektoru se hledají s využitím trénovacích dat.

Trénování probíhá v iteracích 
1. Váhy 𝒘 se nastaví (inicializují) náhodně na malé hodnoty 
2. Na vstup se přivedou postupně všechna trénovací data a na výstupu se tím pádem objeví posloupnost nul a jedniček. Ta se liší od správné posloupnosti - obsahuje chyby.
3. Na základě chyb se zpětně upraví hodnoty vah. 
4. Kroky 2) a 3) se postupně opakují dokud dostatečně klesá chybovost klasifikátoru.

#### MLE
![[MLE - Maximum Likelihood Estimation]]

#### SGD

### Porovnání regrese a logistické regrese

![[Porovnání řešení s SGD.png]]

## SVM
![[SVM - Support Vector Machine]]