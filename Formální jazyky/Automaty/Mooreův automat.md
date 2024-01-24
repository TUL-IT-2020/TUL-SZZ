# Mooreův automat
KA s výstupní funkcí Moorova typu popisujeme uspořádanou šesticí $A = (Q, E, O, G, A, q_o)$, kde:
- Q je konečná neprázdná množina stavů (stavový prostor),
- E je konečná neprázdná množina vstupních symbolů (vstupní abeceda),
- O je konečná neprázdná množina výstupních symbolů,
- G je zobrazení Q x E —> Q (přechodová funkce), 
- A je zobrazení Q —>O (výstupní funkce),
- q_o je počáteční stav (iniciální Stav), $q_o \in Q$.

Výstupní symbol je jednoznačně definován pouze aktuálním stavem. Délka výstupního řetězce je o jedničku větší než délka vstupního řetězce (první znak výstupního řetězce odpovídá počátečnímu stavu).