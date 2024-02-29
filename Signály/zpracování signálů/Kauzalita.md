> [!info] Princip kauzality: 
Odezva nemůže nastat dříve než buzení. Odezva kauzálních systémů závisí pouze na současných a minulých hodnotách. Odezva nekauzálních systémů závisí i na budoucích hodnotách. Nekauzální systémy nejsou realizovatelné v klasických (on-line) systémech. Jsou realizovatelné jen v off‑line režimu, když je celý signál je v paměti. 

> [!example] Příklad nekauzálního systému: 
$$
y(t) = [x(t-1)+x(t)+x(t+1)]/3
$$
