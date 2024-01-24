# Převod ZNKA na DKA
[[Automaty#ZNKA - zobecněný nedeterministický konečný automat|ZNKA]] lze na [[Automaty#DKA - deterministický konečný automat|DKA]] převést přímo (obdoba stromového algoritmu převodu [[Převod NKA na DKA|NKA na DKA]]). Algoritmus je následující: 
1. Určíme si $\epsilon$-uzávěry jednotlivých stavů automatu a tyto uzávěry dále používáme jako stavy v dalších bodech algoritmu. 
2. Vytvoříme kořen stromu spojením všech možných počátečních stavů ($\epsilon$-uzávěrů) do jedné množiny. 
3. Vytvoříme novou vrstvu stromu takovým způsobem, že pro každý stav z příslušné množiny předchozí vrstvy vytvoříme novou množinu všech stavů, které jsou stavem následným po zadání příslušného znaku do automatu. 
4. Pokud jsme v nově vytvořené vrstvě stromu sestavili množinu, která se již v předchozí hierarchii stromu objevila dříve, nebudeme ji již dále rozvíjet (stane se listem stromu).
5. Opakujeme krok číslo 3 tak dlouho, dokud existuje nová množina stavů, která se ještě ve stromové hierarchii neobjevila. 
6. Označíme všechny podmnožiny, které obsahují výstupní stav původního automatu. Tyto množiny se stanou výstupními stavy nového automatu. Počátečním stavem DKA bude podmnožina, která je kořenem stromu. 
7. Jakmile je strom hotov, přejmenujeme jednotlivé podmnožiny na nové označení nového automatu a vytvoříme přechodové funkce (tabulku přechodů). 
8. Nyní můžeme vytvořit stavový diagram nově vzniklého DKA. 

Pokud při tvorbě uzlu podle bodu 3 nenajdeme žádný přechod na některý ze stavů, vzniká prázdná množina { }. Z prázdné množiny se přechází (na všechny symboly abecedy) opět do prázdné množiny (prázdné množiny ve stromu dále nerozvíjíme).