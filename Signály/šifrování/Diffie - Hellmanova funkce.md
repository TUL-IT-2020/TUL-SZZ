# Diffie - Hellmanova funkce
Ustanovení (vytvoření) společného tajemství (klíče).
A: $A_s + B_v$ -> $DH()$ ->klíč $k$
B: $B_s + A_v$ -> $DH()$ ->klíč $k$
$k$ - je totožný klíč

Lze i bez veřejných a soukromých klíčů.

## Možné řešení:
Anča a Bolek si dohodnou (veřejně) čísla $g$ (základ) a $p$ (modul). 
A: vymyslí tajné $a$, vypočte $(g^a \; mod(p)) = A$
B: vymyslí tajné $b$, vypočte $(g^b \; mod(p)) = B$

Anča pošle A a Bolek pošle B.
$B^a = A^b$
protože:
$\left(g^b\right)^a = \left(g^a\right)^b$