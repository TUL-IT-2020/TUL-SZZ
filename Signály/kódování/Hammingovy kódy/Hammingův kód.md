# Hammingův kód
Jinak také: ![[Kód(7,4)]]
$\vec S = (S_1, S_2, S_3, S_4)$ ... zpráva
$\vec x = (S_1, S_2, S_3, S_4,p_1,p_2,p_3)$
- $p_1,p_2,p_3$ ... paritní bity

![[Hamming(7,4).jpg]]
- $p_1 = S_1, S_3, S_4$
- $p_2 = S_1, S_2, S_3$
- $p_3 = S_2, S_3, S_4$

## Generující matice
$$
G = 
\begin{pmatrix}  
1 & 0 & 0 & 0   & 1 &1 &0\\  
0 & 1 & 0 & 0   & 0 &1 &1\\
0 &0&1&0&1&1&1\\
0&0&0&1&1&0&1
\end{pmatrix}
$$
## Kontrolní matice
$$
H = 
\begin{pmatrix}  
1 &0& 1 &1&1&0 &0\\  
1&1&1 & 0&0 & 1&0\\
0&1&1&1&0&0&1
\end{pmatrix}
$$

$$
H * \vec y^T = H * (\vec x  + \vec e)^T = H*\vec x^T = \vec o + H\vec e^T = H\vec e ^T 
$$
Pokud $\vec e$ pouze 1 "1" překopíruje sloupec na dané pozici. 

## Příklad
![[Hammingův kód příklad]]

## (pseudo) Hammingův kód(8,4)
![[(pseudo) Hammingův kód(8,4)]]