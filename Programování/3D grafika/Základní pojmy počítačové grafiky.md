#TODO: Vysvětlit pojmy

> [!tip] Pixel
> Základní obrazový bod. 
>- $[R,G,B]-> [x,y]$
>  
>![[pixel-coordinates.png]]

![[Pixels and Images.png]]


> [!tip] Vertex (vrchol)
![[vertex.svg]]


> [!tip] Fragment
> Velikost stejná jako pixel, ale má ještě informaci o hloubce v obraze.
> - $[r,g,b]$ -> $[x,y,z]$


> [!tip] Vertex Shader
> `C` program určuje jak se mají vrcholy zobrazit.


> [!tip] Fragment Shader


> [!tip] Teselace
> Rozlámání trojúhelníku a vytvoření nových.


> [!tip] Rasterizace (mřížkování)
> Převod trojúhelníku na pixely.


> [!tip] Antialiasing 
> Vyhlazení hran.

## Normála trojúhelníku
Vektorové násobení.
$$
\hat N = cross(v_1 - v_2, v_3 - v_1)
$$
