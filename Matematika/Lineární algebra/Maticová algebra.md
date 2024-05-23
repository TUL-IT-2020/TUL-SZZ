# Maticová algebra 
Maticová algebra je odvětvím algebry, které se zabývá studiem matic a operací s nimi. Matice jsou uspořádané sestavy čísel, které lze používat k reprezentaci lineárních transformací a systémů lineárních rovnic.

****Operace s maticemi:**
- Sčítání matic
- Násobení matice číslem
- Násobení matic
- Transpozice matice
## Typy matic

**Čtvercová matice:**
- Matice, která má stejný počet řádků a sloupců.
$$ A = \begin{bmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \\ 7 & 8 & 9 \\ \end{bmatrix}$$

**Diagonální matice:**
- Matice, kde všechny prvky mimo hlavní diagonály jsou nulové.
$$
D = \begin{bmatrix} 2 & 0 & 0 \\ 0 & 5 & 0 \\ 0 & 0 & 8 \\ \end{bmatrix}
$$
**Symetrická matice:**
- Matice, která je rovna své vlastní transpozici.
$$
B = B' = \begin{bmatrix} 1 & 2 & 3 \\ 2 & 4 & 5 \\ 3 & 5 & 6 \\ \end{bmatrix}
$$
### Inverzní matice #Inverzní_matice
- Inverzní matice je matice, která, vynásobena původní maticí, dává jednotkovou matici. Inverzní matice existuje pouze pro čtvercové matice, pro které determinant není nula.

**Výpočet:** Pro čtvercovou matici \( A \) je inverzní matice \( A^{-1} \) taková, že \( A \cdot A^{-1} = A^{-1} \cdot A = I \), kde \( I \) je jednotková matice.

**Příklad:**
Uvažujme čtvercovou matici
$$C = \begin{bmatrix} 1 & 2 \\ 3 & 4 \\ \end{bmatrix}$$

Vypočteme inverzní matici
$$
C^{-1} = \frac{1}{-2}\begin{bmatrix} 4 & -2 \\ -3 & 1 \\ \end{bmatrix}
$$

Ověříme, že \( C \cdot C^{-1} = C^{-1} \cdot C = I \)
$$
C \cdot C^{-1} = \begin{bmatrix} 1 & 2 \\ 3 & 4 \\ \end{bmatrix} \cdot \frac{1}{-2}\begin{bmatrix} 4 & -2 \\ -3 & 1 \\ \end{bmatrix} = \begin{bmatrix} 1 & 0 \\ 0 & 1 \\ \end{bmatrix} = I
$$


### Determinant #Determinant
- Determinant matice je číslo, které je přiřazeno čtvercové matici. Determinant matice je definován pouze pro čtvercové matice.
- Determinant matice se značí symbolem \( \det(A) \) nebo \( |A| \).
- Determinant matice \( A \) se vypočte jako součet všech možných součinů prvků matice \( A \) a jejich doplňků.

**Výpočet:**
$$
\det(A) = \sum_{\sigma \in S_n} \text{sgn}(\sigma) \prod_{i=1}^n a_{i,\sigma(i)}
$$

**Příklad:**
Uvažujme čtvercovou matici
$$
D = \begin{bmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \\ 7 & 8 & 9 \\ \end{bmatrix}
$$

Vypočteme determinant matice $\det(D)$
$$
\det(D) = 1 \cdot 5 \cdot 9 + 2 \cdot 6 \cdot 7 + 3 \cdot 4 \cdot 8 - 3 \cdot 5 \cdot 7 - 2 \cdot 4 \cdot 9 - 1 \cdot 6 \cdot 8 = 0
$$

### Vlastní čísla a vlastní vektory matic #Vlastní_čísla_a_vlastní_vektory_matic
**Definice:**
Pro čtvercovou matici $A$ a nenulový vektor $\mathbf{v}$ platí, že $\lambda$ je vlastní číslo matice $A$, a $\mathbf{v}$ je vlastní vektor příslušný $\lambda$, pokud platí rovnice $A\mathbf{v} = \lambda\mathbf{v}$. Vlastní čísla a vlastní vektory hrají důležitou roli ve studiu lineárních transformací a analýze systémů lineárních rovnic.

**Výpočet:**
1. **Charakteristický polynom:**
   - Charakteristický polynom matice $A$ se získá výpočtem determinantu matice $A - \lambda I$, kde $\lambda$ je neznámá.
   - Charakteristický polynom $\det(A - \lambda I) = 0$ určuje vlastní čísla $\lambda$.
   - Pro čtvercovou matici $A$ řádu $n$ je charakteristický polynom stupně $n$.
2. **Nalezení vlastních vektorů:**
   - Pro každé vlastní číslo $\lambda$ řešíme soustavu rovnic $(A - \lambda I)\mathbf{v} = \mathbf{0}$, kde $\mathbf{v}$ jsou neznámé vlastní vektory.
   - Pro každé vlastní číslo $\lambda$ může existovat více vlastních vektorů.
   - Vlastní vektory jsou nenulové vektory, které jsou řešením soustavy rovnic $(A - \lambda I)\mathbf{v} = \mathbf{0}$.
   - Vlastní vektory jsou lineárně závislé.
  
**Praktická interpretace:**
- Vlastní čísla mohou reprezentovat změnu měřítka nebo faktory dilatace v lineární transformaci matice.
- Vlastní vektory ukazují směr, ve kterém se daná transformace rozšiřuje nebo stlačuje.

**Příklad:**
Uvažujme matici
$$
A = \begin{bmatrix} 3 & 1 \\ 1 & 3 \\ \end{bmatrix}
$$

Pro nalezení vlastních čísel provedeme výpočet charakteristického polynomu:
$$
\det(A - \lambda I) = \begin{vmatrix} 3 - \lambda & 1 \\ 1 & 3 - \lambda \\ \end{vmatrix} = (3 - \lambda)^2 - 1 = \lambda^2 - 6\lambda + 8 = (\lambda - 4)(\lambda - 2) = 0
$$

Odtud máme dvě vlastní čísla $\lambda_1 = 4$ a $\lambda_2 = 2$. Nyní můžeme najít odpovídající vlastní vektory pro každé z těchto čísel.

**Pro $\lambda_1 = 4$**

Řešíme soustavu rovnic $(A - \lambda I)\mathbf{v} = \mathbf{0}$:
$$
(A - \lambda I)\mathbf{v} = \begin{bmatrix} 3 - 4 & 1 \\ 1 & 3 - 4 \\ \end{bmatrix}\mathbf{v} = \begin{bmatrix} -1 & 1 \\ 1 & -1 \\ \end{bmatrix}\mathbf{v} = \mathbf{0}
$$

Řešení soustavy rovnic je $\mathbf{v} = \begin{bmatrix} 1 \\ 1 \\ \end{bmatrix}$. Vlastní vektor $\mathbf{v}$ je nenulový vektor, který je řešením soustavy rovnic $(A - \lambda I)\mathbf{v} = \mathbf{0}$.

**Pro $\lambda_2 = 2$**

Řešíme soustavu rovnic $(A - \lambda I)\mathbf{v} = \mathbf{0}$:
$$
(A - \lambda I)\mathbf{v} = \begin{bmatrix} 3 - 2 & 1 \\ 1 & 3 - 2 \\ \end{bmatrix}\mathbf{v} = \begin{bmatrix} 1 & 1 \\ 1 & 1 \\ \end{bmatrix}\mathbf{v} = \mathbf{0}
$$

Řešení soustavy rovnic je $\mathbf{v} = \begin{bmatrix} -1 \\ 1 \\ \end{bmatrix}$. Vlastní vektor $\mathbf{v}$ je nenulový vektor, který je řešením soustavy rovnic $(A - \lambda I)\mathbf{v} = \mathbf{0}$.

