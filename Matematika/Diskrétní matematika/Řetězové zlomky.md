# Řetězové zlomky
Spadají do oblasti matematiky zvané diofantická aproximace. Řetězovým zlomkem rozumíme výraz (koneční nebo nekonečný) tvaru: 
$$
q0 + \frac{1}{
q1 + \frac{1}{
q2 + \frac{1}{q3 + · · ·}
}}
$$

kde:
- $q_0 \in Z$, 
- $q_i \in N$ pro $i = 1, 2, ....$ 

Čísla $q_i$ jsou tzv. členy řetězového zlomku. 
Číslo $x$ vyjádřené pomocí řetězových zlomků s členy $q_0$ až $q_n$ můžeme zapsat též jako: 
$x = [q0, q1, ..., qn]$

## Definice: přibližný zlomek
i-tý přibližný zlomek má tvar: 
$$
δ_i = \frac{P_i} {Q_i} 
$$
Kde: 
- $P_i$ je čitatel, 
- $Q_i$ je jmenovatel i-tého přibližného zlomku


Pro hledání přibližných zlomků je vhodné sestavit tabulku přibližných zlomků: 

| i | -1 | 0 | 1 | 2 | · · · | n − 1 | n |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| qi | \\ | q0 | q1 | q2 | · · · | qn−1 | qn |
| Pi | 1 | q0 | q_1q_0 + 1 | q2P1 + P0 | · · · | qn−1Pn−2 + Pn−3 | qnPn−1 + Pn−2 |
| Qi | 0 | 1 | q_1q_0 + 1 | q2Q1 + Q0 | · · · | qn−1Qn−2 + Qn−3 | qnQn−1 + Qn−2 |
Při určování hodnot se využívá již uvedených rekurentních vztahů.