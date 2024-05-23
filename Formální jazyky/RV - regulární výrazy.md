# Regulární výrazy
Pro operace s RV platí priorita operací:
1) iterace (*) … nejvyšší priorita
2) zřetězení (ꞏ) … obvykle se tečka v RV vynechává
3) sjednocení (+) … nejnižší priorita

## Pravidla pro operace s RV
$R, S, T \in RV(\Sigma)$
1) $R + S = S + R$
2) $(R + S) + T = R + (S + T)$
3) $R + \emptyset = R$
4) $R + R = R$
5) $R(S + T) = RS + RT$
6) $(RS)T = R(ST)$
7) $R^0 = \epsilon$
8) $R^* = \epsilon + R^*$
9) $(RS)^*R = R(SR)^*$
10) $(R + S)^* = (R^* + S^*)^* = (R^*S^*)^*$