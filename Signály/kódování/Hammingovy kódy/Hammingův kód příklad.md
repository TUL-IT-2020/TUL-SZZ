# Příklad
#příklad 
Zprávy:
$S_1 = 1011$ $x_1 = 1011\; 100$
$S_2 = 0001$ $x_2 = 0001\; 101$
$S_3 = 1111$ $x_3 = 1111\; 111$
$S_4 = 0000$ $x_4 = 0000\; 000$

Příchozí:
$y_1 = 1011\; 100$
$y_1' = 0011\; 100$
$y_2 = 0001\; 001$
$y_3 = 1011\; 101$

Nakresli si Vennův diagram!
![[Hamming_y_1.png]]

$$
H = 
\begin{pmatrix}  
1 &0& 1 &1&1&0 &0\\  
1&1&1 & 0&0 & 1&0\\
0&1&1&1&0&0&1
\end{pmatrix} * 
\begin{pmatrix}  
0&0\\
0&0\\
1&0\\
1&1\\
1&0\\
0&0\\
0&1
\end{pmatrix}
= \begin{pmatrix} 
1&1&0\\
1&0&0
\end{pmatrix}
$$
1. sloupec chyba v 1. bitu.
Chyba v 5. bitu
