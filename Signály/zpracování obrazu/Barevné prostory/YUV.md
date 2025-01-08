# YUV
Vhodný pro přenos barevné informace. Analogové (TV).

> [!example] YUV
>- Y – jas, 
>- U – modrá projekce, 
>- V – červená projekce

> [!example] Y’UV
>- Y’ – luma (vážený jas po gamma korekci), 
>- U, 
>- V – chroma modré a červené projekce (-/+)

Převod záleží na standardu YUV

## YIQ (NTSC)

> [!tip] RGB -> YIQ
$$
\begin{bmatrix}
Y \\ 
I \\ 
Q
\end{bmatrix}
=
\begin{bmatrix}
0.299 & 0.587 & 0.114 \\ 
0.596 & -0.274 & -0.322 \\ 
0.211 & -0.523 & 0.312
\end{bmatrix}
\begin{bmatrix}
R \\ 
G \\ 
B
\end{bmatrix}
$$
