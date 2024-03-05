# Shaker sort (koktejlové řazení)
Je to vylepšení BubbleSortu. Na rozdíl od BubbleSortu neřadí pouze jedním směrem, ale oběma (zabrání se tak problému želv a zajíců BubbleSortu – vysoké hodnoty probublávají na konec rychlé, ale ty nízké postupují na začátek velmi pomalu). Stejně jako BubbleSort má vnořené cykly – hlavní iterační a vedlejší porovnávací. Hlavní iterační probíhá jen n/2 krát – každá iterace obsahuje dvě fáze:
1. Při dopředené stoupá nejlehčí bublinka vzhůru
2. Při zpětné klesá nejtěžší bublinka ke dnu

> [!info] Složitost: $O(N^2)$

