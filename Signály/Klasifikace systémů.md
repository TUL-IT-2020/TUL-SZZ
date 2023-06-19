# Klasifikace systémů

## Klasifikace systémů podle charakteru signálů
- **Spojité systémy** pracují se spojitými vstupními a výstupními signály. 
- **Číslicové systémy** pracují s diskrétními signály. 
- **Hybridní systémy** fungují jako převodníky mezi analogovými a číslicovými signály. 

## Klasifikace systémů podle kauzality 
Princip kauzality: odezva nemůže nastat dříve než buzení. Odezva kauzálních systémů závisí pouze na současných a minulých hodnotách. Odezva nekauzálních systémů závisí i na budoucích hodnotách. Nekauzální systémy nejsou realizovatelné v klasických (on-line) systémech. Jsou realizovatelné jen v off‑line režimu, když je celý signál je v paměti. Příklad nekauzálního systému: 

$$
y(t) = [x(t-1)+x(t)+x(t+1)]/3
$$

## Klasifikace systémů podle linearity 
Odezva na lineární kombinaci budících signálů je rovna lineární kombinaci odezev na jednotlivé budící signály. Z linearity vyplývá princip superpozice (odezvu systému lze složit s odezev na dílčí buzení). 
- Příklad lineárních systémů: $y(t) = k * x(t)$ 
- Příklad nelineárních systémů: $y(t) = x^2 (t)$

## Klasifikace systémů podle časové nezávislosti (stacionarity)
Pro časově nezávislý systém platí podmínka: . Je-li vstupní signál zpožděn o čas , musí být i výstup zpožděn o čas . Chování systému se nemění v čase. 
- Příklad časově nezávislých systémů: $y(t) = k * x(t)$ 
- Příklad časově závislých systémů: $y(t) = t * x(t)$