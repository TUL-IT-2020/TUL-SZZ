#MVD 
# PageRank
Hodnotí stránku dle její popularity. Intuice: Linky jsou podobné jako citace v literatuře. U často citované stránky je očekáváno, že bude užitečnější. PageRank počítá citace, ale své počítání rozšiřuje o: 
- Váhu citací
- Vyhlazení počtu citací. U každé stránky se uvažuje nenulový počet citací

PageRank si lze představit jako výpočet pravděpodobnosti náhodného surfování. Data jsou reprezentována orientovaným grafem. 
- Uzly – stránky
- Hrany – linky

Pro graf vytvoříme matici přechodů s pravděpodobnostmi přechodu do jiného uzlu:
$$
\sum^N_{𝑗=1} 𝑀_{𝑖𝑗} = 1
$$
$M_{ij}$ = pravděpodobnost přechodu z $d_i$ do $d_j$

Model s parametrem $\alpha$:
- S pravděpodobností $\alpha$ skočíme náhodně na jinou stránku.
- S pravděpodobností $(1 - \alpha)$ náhodně vybereme link na současné stránce

$p(di)$: PageRank skóre pro $d_i$ = průměrná pravděpodobnost návštěvy stránky $d_i$
$$
\vec p = ((1 - \alpha) M + \frac{\alpha} {N} E)^T \vec p  
$$
$𝐸_{𝑖𝑗} = 1$, jednotková matice (nikoliv identita)

Problém se stránkou, která má 0 výstupních hran (0 linků). Suma pravděpodobností nemůže být 1. Řešením je úprava parametru $\alpha$, tak že $\alpha = 1$, pro stránky s 0 linky.