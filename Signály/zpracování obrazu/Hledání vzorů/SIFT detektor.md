# SIFT detektor

Scale Invariant Feature Tranform 
Distinctive image features from scale-invariant keypoints (2004). Původní článek z roku 1999 jeden z prvních na téma rozpoznávání podobnosti obrázků na základě korespondence lokálních příznaků. Velmi úspěšná & robustní metoda.

1. Detekce lokálních maxim v prostoru měřítek jako možných zájmových bodů 
2. Lokalizace a filtrace zájmových bodů 
3. Přiřazení orientace zájmovým bodům 
4. Výpočet deskriptorů z okolí zájmových bodů

K určování zájmových bodů využívá hledání rohů. 
- [[Detekce rohů]]

## Lokální korespondence

Abychom mohli např. zarovnat obrazy, potřebujeme vědět, který zájmový bod na obraze 1 odpovídá jakému v obraze 2. Nejjednodušší postup je hladový algoritmus, kdy ke každému $𝒙_𝑞$ z “query” obrazu 1 přiřadíme nejpodobnější 𝒙 z obrazu 2. (Ne)podobnost může být např. L2 vzdálenost.

Je obtížné stanovit práh na vzdálenost mezi $𝒙_𝑞$ a nejbližším deskriptorem z druhého obrazu $𝒙_{1𝑁𝑁}$. Namísto toho zvážíme ještě druhý nejpodobnější deskriptor $𝒙_{2𝑁𝑁}$. Dobrý test, zda $𝒙_𝑞$ a $𝒙_{1𝑁𝑁}$ reprezentují stejný bod, je poměr vzdáleností:
$$
r = \frac
{|| x_q - x_{1NN} ||}
{|| x_q - x_{2NN} ||}
$$