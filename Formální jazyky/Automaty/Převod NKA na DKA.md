# Převod NKA na DKA
Všechny NKA je možné převést na DKA. Je zapotřebí „pouze” sjednotit vstupní stavy do jednoho deterministického vstupu a definovat nové vnitřní stavy, které budou odpovídat všem variacím z nedeterministické množiny.

Původní množinu stavů nahradíme její potenční množinou P(Q). Ta obsahuje všechny podmnožiny množiny P, kterých je 2Q, kde Q je počet prvků původní množiny. 

Počet stavů DKA může být tedy až 21, kde n je počet stavů NKA (při převodu nás zajímají jen dosažitelné podmnožiny).

## Algoritmus převodu NKA na DKA
Stromový algoritmus převodu NKA na DKA (determinizace):
1. Vytvoříme kořen stromu spojením všech možných počátečních stavů (z množiny l) do jedné množiny.
2. Vytvoříme novou vrstvu stromu takovým způsobem, že pro každý stav z příslušné množiny předchozí vrstvy vytvoříme novou množinu všech stavů, které jsou stavem následným po zadání příslušného znaku do automatu.
3. Pokud jsme v nově vytvořené vrstvě stromu sestavili množinu, která se již v předchozí hierarchii stromu objevila dříve, nebudeme ji již nijak dále rozvíjet (stane se listem stromu). Množiny jsou jednoznačně určeny pouze svými prvky, nikoliv jejich pořadím (množiny {$q_1, q_3, q_5$} a {$q_3, q_1, q_5$} jsou stejné).
4. Opakujeme krok číslo 2 tak dlouho, dokud existuje nová množina stavů, která se ještě ve stromové hierarchii neobjevila.
5. Označíme všechny podmnožiny, které obsahují výstupní stav původního automatu. Tyto množiny se stanou výstupními stavy nového automatu. Počátečním stavem DKA bude podmnožina, která je kořenem stromu.
6. Jakmile je strom hotov, přejmenujeme jednotlivé podmnožiny na nové označení nového automatu a vytvoříme přechodové funkce.
7. Nyní můžeme vytvořit stavový diagram nově vzniklého DKA.

Pokud při tvorbě uzlu podle bodu 2 nenajdeme žádný přechod na některý ze stavů, vzniká prázdná množina { }. Z prázdné množiny se přechází (na všechny symboly abecedy) opět do prázdné množiny — ošetřuje se tím chybová situace v automatu („zaseknutí”).