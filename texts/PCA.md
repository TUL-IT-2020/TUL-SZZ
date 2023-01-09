#MVD 
# PCA
Principal Component Analysis slouží k dekorelaci příznaků nebo k redukci počtu příznaků.
1. Normalizujeme data $X$ 
2. Vypočteme kovarianční matici dat $𝜮𝑿$ 
3. Vypočteme vlastní čísla 𝝀 a vlastní vektory 𝒗 kovarianční matice $𝜮𝑿$ 
4. Vybereme n vlastních vektorů příslušejících n největším vlastním číslům (vznikne menší matice V obsahující vlastní vektory) 
5. Transformujeme data do nižší dimenze $𝑍 = 𝑋V$