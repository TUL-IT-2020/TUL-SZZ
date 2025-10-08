# Vlastní čísla a vlastní vektory matic

**Definice:**
Pro čtvercovou matici $A$ a nenulový vektor $\mathbf{v}$ platí, že $\lambda$ je vlastní číslo matice $A$, a $\mathbf{v}$ je vlastní vektor příslušný $\lambda$, pokud platí rovnice $A\mathbf{v} = \lambda\mathbf{v}$. Vlastní čísla a vlastní vektory hrají důležitou roli ve studiu lineárních transformací a analýze systémů lineárních rovnic.

**Výpočet:**
1. **Charakteristický polynom:**
   - Charakteristický polynom matice $A$ se získá výpočtem determinantu matice $A - \lambda I$, kde $\lambda$ je neznámá.
   - Charakteristický polynom $\det(A - \lambda I) = 0$ určuje vlastní čísla $\lambda$.

2. **Nalezení vlastních vektorů:**
   - Pro každé vlastní číslo $ \lambda $ řešíme soustavu rovnic $(A - \lambda I)\mathbf{v} = \mathbf{0}$, kde $\mathbf{v}$ jsou neznámé vlastní vektory.

**Praktická interpretace:**
- Vlastní čísla mohou reprezentovat změnu měřítka nebo faktory dilatace v lineární transformaci matice.
- Vlastní vektory ukazují směr, ve kterém se daná transformace rozšiřuje nebo stlačuje.

**Příklad:**
Uvažujme matici
$$
A = \begin{bmatrix}
3 & 1 \\
1 & 3 \\
\end{bmatrix}
$$
Pro nalezení vlastních čísel provedeme výpočet charakteristického polynomu:
$$
\det(A - \lambda I) = \begin{vmatrix}
3 - \lambda & 1 \\
1 & 3 - \lambda \\
\end{vmatrix} = (\lambda - 4)(\lambda - 2) = 0
$$
Odtud máme dvě vlastní čísla $\lambda_1 = 4$ a $\lambda_2 = 2$. Nyní můžeme najít odpovídající vlastní vektory pro každé z těchto čísel.
