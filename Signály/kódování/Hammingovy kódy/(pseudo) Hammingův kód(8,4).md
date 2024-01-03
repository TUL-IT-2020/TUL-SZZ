## (pseudo) Hammingův kód(8,4)
Pracuje s dvojitými chybami korektně
![[Hamming(8,4).svg.png]]
Dvojitá chyba:
p_4 souhlasí
p_1 - p_3 ukazají chybu.
Nelze ji opravit, ale lze jí opravit.

Není dokonalý
8bitů = 256 potenciálních slov
16 kódových slov délky 8
16x8 = 128 sousedů
128 + 16 = 144 < 256

Kód s vlastností **SEC/DEC** (single error correction, double error detection)
Současně:
1 chyba -> oprava
2 chyby -> detekce