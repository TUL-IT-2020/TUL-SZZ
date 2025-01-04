$G = (V,H)$ souvislý hranově ohodnocený graf.
$C: H -> R^+$ 
- $c(h)$ - kapacita hrany

V daném grafu najděte uzavřený sled nejmenší možné váhy, který obsahuje každou hranu daného grafu.

Jak řešit v případě grafu, který není Eulerovský?

Párování
Párfektní párování

- S - vrcholy lichého stupně
- $|S|$ - je sudý (spojitý graf) 

## Algoritmus
Vytvoříme $K_S$ - úplný graf na S.
Každé hraně přiřadíme ohodnocení hran zvané minimální délka cesty v grafu G.
V $K_S$ nalezneme perfektním párováním minimální váhy (odpovídají nejkratší cesty mezi vrcholy množiny S).
Nyní přidáme paralelní hrany podél nejkratších cest tvořící perfektní minimální párování.

-> vznikne graf s vrcholy sudého stupně a je tedy Eulerovský.
