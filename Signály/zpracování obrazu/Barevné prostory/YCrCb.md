# YCrCb
Digitální reprezentace
- Y’ – luma (vážený jas po gamma korekci), 
- Cr, Cb – chroma modré a červené projekce

V počítačích často označováno jako YUV

> [!info] Formáty a pořadí ukládání:
>- YUV444 – 3 byte / pix
>- YUV422 – 4 byte / 2 pix
>- YUV411 – 6 byte / 4 pix
>- YUV420p – 6 byte / 4 pix

RGB888 → YUV444

> [!tip] Konverze z RGB -> YCbCR
$$
\begin{bmatrix} Y \\ Cb \\ Cr \end{bmatrix} = \begin{bmatrix} 0.299 & 0.587 & 0.114 \\ -0.168736 & -0.331264 & 0.5 \\ 0.5 & -0.418688 & -0.081312 \end{bmatrix} \begin{bmatrix} B \\ G \\ R \end{bmatrix} + \begin{bmatrix} 16 \\ 128 \\ 128 \end{bmatrix}
$$
