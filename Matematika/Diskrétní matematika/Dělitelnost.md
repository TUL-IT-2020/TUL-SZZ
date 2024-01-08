# Dělitelnost
## Definice: Být dělitelem
Řekneme, že nenulové celé číslo b dělí celé číslo a, píšeme $b\mid a$, jestliže:
$$
(\exists q \in Z)(a = b*q)
$$
V opačném případě píšeme $b\nmid a$ a říkáme, že b nedělí a.

Využívané pojmy: 
- a - dělenec čísla b 
- b - dělitel čísla a 
- q - podíl čísla a při dělení číslem b 
- | - relace na Z (event. N)

## Věta o dělení se zbytkem: 
Nechť a ∈ Z, b ∈ N +. Potom existuje jediná dvojce čísel q, r ∈ Z taková, že $a = b · q + r$, kde 0 ≤ r < b. 

Využívané pojmy: 
- q - neúplný podíl 
- r - zbytek

## Převody mezi číselnými soustavami
 - $b \in N^+$, 
 - $a \in N$

Každé číslo a lze vyjádřit jednoznačným způsobem (plyne z věty o dělení se zbytkem) jako:
$$
a = r_0 + r_1b + r_2b^2 ... = \sum^{n}_{i=0} r_ib^i
$$
kde $r_i \in {0, 1, ..., b − 1} ∧ r_n \neq 0$. 

Čísla $r_i$ se nazývají cifry čísla $a$ a $b$ představuje základ soustavy. (Běžně se převod realizuje s mezičlánkem přes desítkovou soustavu). Z desítkové na cílovou pak opakováním: 
$$
a = (r_1 + r_2b + ... + r_nb^{n−1} + r_0)b
$$

Příklad: [[Převody soustav příklad]]

