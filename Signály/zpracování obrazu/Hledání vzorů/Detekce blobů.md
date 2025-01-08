# Detekce blobů

Ve 2D je operátor $∇^2𝑔_𝜎(𝑥)$ nahrazen tzv. Laplaciánem Gaussiánu (Laplacian of Gaussian, LoG)

![[LoG]]

## Detekce blobů ve 2D
- [[Konvoluce v obraze]]

1. Obrázek $𝐼(𝑥, 𝑦)$ konvolvujeme s LoG filtry $∇^2𝑔_𝜎$ s různými $𝜎 = 𝜎1, … , 𝜎_s$.
2. Bloby, tj. jejich pozice a velikost, najdeme lokální maxima funkce $∇^2_{norm} 𝐿(𝑥, 𝑦, \sigma)$.