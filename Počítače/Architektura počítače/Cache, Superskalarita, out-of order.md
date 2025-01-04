# Cache, Superskalarita, out-of order
Máme pipelinovaný RISC procesor vykonávající program. 

Zasekne se na načítání z paměti, závislosti ve výpočtu, ...
-> STALL

> [!question] Co s tím?
STALL musí být odstraněn!
## Cache
Data jsou nahrána/uložena do rychlé paměti
Až je budeme potřebovat, budou tam (možná)
## Superskalarita
Přidáme víc ALU
Když budeme mít data, zpracujeme je paralelně

![[Superscalar CPU.png]]
## Kompilátor
Přetřídíme instrukce
## Out-of order
Čekajíce na data, zpracujeme další instrukci
Závislosti!!!
