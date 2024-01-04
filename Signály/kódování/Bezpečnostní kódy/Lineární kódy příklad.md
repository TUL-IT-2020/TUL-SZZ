#příklad 
Zpráva: 110 001 111
$\vec s_1 = 110$
$\vec s_2= 001$
$\vec s_3 = 111$

$$
G = 
\begin{pmatrix}  
1 & 0 & 0 & 1\\  
0 & 1 & 0 & 1\\
0 & 0 & 1 & 1\\
\end{pmatrix}
$$
$$
\vec x = \vec s_1 * G = (110) (...) = (1100)
$$
$$
\vec x = \vec s_2 * G = (001) (...) = (0011)
$$
$H = (1111)$

$\vec y_1 = (1100)$
$\vec y_2 = (1011)$

$$H * \vec y_1 = (1111)*(1100)^T = 2 \pmod 2 =0$$
$$H * \vec y_2 = (1111)*(1011)^T = 3 \pmod 2 = 1 \rightarrow chyba$$
