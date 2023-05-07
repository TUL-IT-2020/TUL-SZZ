#MVD 
# Metriky
## Minkowského vzdálenost
Minkowského vzdálenostní funkce tvoří celou rodinu metrických funkcí určených jako $L_p$ metriky, protože jednotlivé případy závisí na číselných parametrech $p$. Tyto funkce jsou definované na n-rozměrných vektorech reálných čísel jako:
$$
L_p \left[ (x_1,...,x_n), (y_1,...,y_n) \right] = 
\sqrt[p]{\sum |{x_i - y_i}|^p }
$$
Kde $L_1$ metrika je známá jako Manhattanská vzdálenost, $L_2$ vzdálenost značí známou Euklidovskou vzdálenost, a $L_{\infty} = max^{n}_{i=1} \left| x_i - y_i \right|$ je nazývána Chebyshevova neboli šachovnicová vzdálenost.

## Euklidovská vzdálenost (Euclidean dist.) 
$$
𝑑(𝒙, 𝒛) = \sum^P_{𝑖=1} \sqrt{(𝑥_𝑖 − 𝑧_𝑖 )^2}
$$
Euklidovská vzdálenost je z rodiny $L_p$ metrik nejpoužívanější. V případě, že by objekty byly charakterizovány pouze dvěma znaky, pak je lze zakreslit jako bod v rovině a Euklidovská vzdálenost je definována jako délka úsečky spojující příslušné dva body. Tato vzdálenost je vhodná k použití v situacích, kdy měřené znaky jsou nezávislé, normálně rozdělené se stejnými rozptyly a v případech, kdy znaky jsou věcně podobné a stejně důležité pro klasifikaci dat.

## Vzdálenost v městských blocích (Manhattan dist.) 
$$
𝑑(𝒙, 𝒛) = \sum^P_{𝑖=1} \lvert{𝑥_𝑖 − 𝑧_𝑖 \rvert}
$$
Manhattanská vzdálenost někdy také zvaná newyorská metrika, byla inspirována
pravoúhlým systémem ulic na Manhattanu. V dvourozměrném pozorování, jde o vzdálenost dvou
bodů v rovině měřenou po odvěsnách pravoúhlého trojúhelníku, zatímco euklidovská vzdálenost je
měřená po přeponě.
![Manhatanovská metrika](http://home.ef.jcu.cz/~klufova/GIS/GIS1/_book/pictures/blokova_metrika.png)

## Šachovnicová vzdálenost
Šachovnicová vzdálenost (D8) je založena na principu osmisousedství. Pixely spojené úsečkou jsou tak od sebe vzdáleny dva pixely. Této metriky lze využít při výpočtu diagonální vzdálenosti. Pro šachovnicovou vzdálenost platí vztah:
$$
D_8(p,q) = max(|x_1-y_1| + |x_2-y_2|)
$$

## Zdroje:
https://www.vut.cz/www_base/zav_prace_soubor_verejne.php?file_id=116923
http://home.ef.jcu.cz/~klufova/GIS/GIS1/_book/rastrová-data.html
https://dspace.tul.cz/bitstream/handle/15240/25271/DP_Jelinek_2015.pdf?sequence=-1